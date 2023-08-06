We know that computer stores data in the form of 0s and 1s. 
In a more refined language, computer operates in binary.

However, what you should know here is that binary is a number system, much like the decimal number system which we use.

Which means that the only thing it can store is numbers.

But right now you're reading this, presumably on your computer screen and this text isn't numbers is it?

So how does computer do that? Well the answer to that is, that the program internally stores the kind of the data which is being entered. How does computer know, it doesn't, the programmer told it, by specifying the data type of the data being entered. 

There are multiple types of data in C.
Primarily, there are 6
1. Integer numbers
2. Real numbers
3. Characters
4. Pointers
5. Sum Type (Enums) (User defined)
6. Product Type (Structs) (User defined)

For now we're gonna focus our attention on the first 3, since the other 3 require a book of their own to be explained properly (There even exists one on pointers in C)

First let's look at integer type, There are 2 kinds of integers, unsigned integers (fancy name for whole numbers) and signed integers (normal integers)

Then there are four variants of each of these 2 subtypes.
- Unsigned:
	1. `unsigned short int`
	2. `unsigned int`
	3. `unsigned long int`
	4. `unsigned long long int`
- Signed:
	1. `short int`
	2. `int`
	3. `long int`
	4. `long long int`

Now you may be wondering, what on earth is the purpose of having four types? Well the answer is back in the day, computers had very limited memory, hence you wanted to use as little of it as possible. 

Therefore these conventions were made keeping in mind that, you only have a limited amount of memory.

An `unsigned short int` or a `short int` would use one or two bytes of memory, depending upon system, `unsigned int` or `int` would use either 2 bytes or 4 bytes of memory, `unsigned long int` or `long int` would use 4 bytes or 8 bytes, and finally `unsigned long long int` or `long long int` would use 8 bytes of memory always.

Now a days, for most PCs memory isn't an issue, unless it's in GB or GiB, but back then it was, hence the inconsistency.

On most of the modern systems the values have been fixed, but in some of the older systems the issue persists hence the need of clarification.

The issue with this kind of thing of course is that it murders portability. Hence we have the `inttypes.h` header file, which gives us integers with standard sized to work with, following is the table depicting the size, version, name and range of the type.

|size(bits)|usigned|signed|range unsigned|range signed|
|:--------:|:-----:|:----:|:------------:|:----------:|
|8|uint8_t|int8_t|0 to 255| -128 to 127 |
|16|uint16_t|int16_t|0 to 65,535| -32,768 to 32,767|
|32|uint32_t|int32_t|0 to 4,294,967,295| -2,147,483,648 to 2,147,483,647 |
|64|uint64_t|int64_t|0 to 18,446,744,073,709,551,615| -9,223,372,036,854,775,808 to 9,223,372,036,854,775,807|
|word|size_t|ssize_t| NA | NA|

Moving on to real numbers, there are two divisions in that float and double. Real numbers can store values from -&infin; to &infin; at the cost of precision. floats or single precision floating point numbers take 32 bits of memory and can store numbers with upto 7 significant figures, and doubles or double precision floating point numbers can store upto 15 significant figures. Why? Well, it's too off topic but if you wanna know, lookup IEEE Standard 754 Floating Point Numbers.

Moving to characters, There are two types of characters unsigned and signed. What? How can characters be signed and unsigned? Well... Characters actually are spiritual brother of Integers. As discussed earlier, all the data stored in the computer is in binary format, and (since characters can't actually exist in binary number system), how characters are stored internally is basically like an integer. The only thing is when they're displayed, a lookup table is used to get the glyph which should be shown on screen based on the value of the character. 
A character in C takes 1 byte, and follows ASCII table (given below)

|DEC|HEX|CHAR|
|:-:|:-:|:--:|
|0|00|NUL|
|1|01|SOH|
|2|02|STX|
|3|03|ETX|
|4|04|EOT|
|5|05|ENQ|
|6|06|ACK|
|7|07|BEL|
|8|08|BS|
|9|09|HT|
|10|0A|LF|
|11|0B|VT|
|12|0C|FF|
|13|0D|CR|
|14|0E|SO|
|15|0F|SI|
|16|10|DLE|
|17|11|DC1|
|18|12|DC2|
|19|13|DC3|
|20|14|DC4|
|21|15|NAK|
|22|16|SYN|
|23|17|ETB|
|24|18|CAN|
|25|19|EM|
|26|1A|SUB|
|27|1B|ESC|
|28|1C|FS|
|29|1D|GS|
|30|1E|RS|
|31|1F|US|
|32|20|space|
|33|21|!|
|34|22|"|
|35|23|#|
|36|24|$|
|37|25|%|
|38|26|&|
|39|27|'|
|40|28|\(|
|42|2A|\*|
|43|2B|+|
|44|2C|,|
|45|2D|-|
|46|2E|.|
|47|2F|/|
|48|30|0|
|49|31|1|
|50|32|2|
|51|33|3|
|52|34|4|
|53|35|5|
|54|36|6|
|55|37|7|
|56|38|8|
|57|39|9|
|58|3A|:|
|59|3B|;|
|60|3C|\< |
|61|3D|=|
|62|3E|\>|
|63|3F|?|
|64|40|@|
|65|41|A|
|66|42|B|
|67|43|C|
|68|44|D|
|69|45|E|
|70|46|F|
|71|47|G|
|72|48|H|
|73|49|I|
|74|4A|J|
|75|4B|K|
|76|4C|L|
|77|4D|M|
|78|4E|N|
|79|4F|O|
|80|50|P|
|81|51|Q|
|82|52|R|
|83|53|S|
|84|54|T|
|85|55|U|
|86|56|V|
|87|57|W|
|88|58|X|
|89|59|Y|
|90|5A|Z|
|91|5B|\[|
|92|5C|\\|
|93|5D|\]|
|94|5E|\^|
|95|5F|\_|
|96|60|\`|
|97|61|a|
|98|62|b|
|99|63|c|
|100|64|d|
|101|65|e|
|102|66|f|
|103|67|g|
|104|68|h|
|105|69|i|
|106|6A|j|
|107|6B|k|
|108|6C|l|
|109|6D|m|
|110|6E|n|
|111|6F|o|
|112|70|p|
|113|71|q|
|114|72|r|
|115|73|s|
|116|74|t|
|117|75|u|
|118|76|v|
|119|77|w|
|120|78|x|
|121|79|y|
|122|7A|z|
|123|7B|{|
|124|7C|\||
|125|7D|}|
|126|7E|~|
|127|7F|DEL|

Now a days, ASCII has been replaced with UTF-8 and in some places even UTF-16, but in C, ASCII remains to be the standard due to backward compatibility. If C were to change it now, within a day, Windows, Linux, Android e.tc. will all die with no way to restore them for months to say the least. That's how sensitive the issue is, so the C devs decided not to touch it.
