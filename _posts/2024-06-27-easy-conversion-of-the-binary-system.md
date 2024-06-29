---
title: "Easy Conversion of the Binary system of IPv4 addresses and Subnet masks."
date: 2024-06-27
categories: [Networking]
tag: [binary, ipv4-address, subnet-mask]
description: Understanding the binary system conversion of IPv4 addressing.
---

## Binary System of IPv4 Address

In the world of computers and networks, IP addresses and subnet masks in decimal format are meaningless. This is because computers and networks only understand them in a binary format. Binary numbers are made up of 1s and 0s and these are called bits. For example, the binary numbers of the IPv4 address 192.168.0.1 and subnet mask 255.255.255.0 respectively are;

        192     .168     .0        .1
        11000000.10101000. 00000000.00000001

        255     .255     .255     .0
        11111111.11111111.11111111.00000000

The next action is to find out how to easily get the binary numbers of the IP addresses and the subnet masks.

### The 8bit Octet chart

The 8 bit octet chart is gotten from the powers of base 2, that is 2<sup>x</sup>, where x is 0, 1, 2, etc.

Since, there are 8 bits, we will need only the powers of 0 to 7.

{: .prompt-tip }

> - 2<sup>0</sup> = 1
> - 2<sup>1</sup> = 2
> - 2<sup>2</sup> = 4
> - 2<sup>3</sup> = 8
> - 2<sup>4</sup> = 16
> - 2<sup>5</sup> = 32
> - 2<sup>6</sup> = 64
> - 2<sup>7</sup> = 128

Arrange it from the right to the left, we have the 8 bit octet chart.

         128  64  32 16  8  4  2  1

**NOTE;**

{: .prompt-info }

> - The bit in each octet is represented by a number from the chart
>
> - Starting from the right, the first bit is a value of 1, and it doubles with each step till it gets to the value of 128.
>
> - The bit from the octet can only be 1 or 0.
>
> - If the bit is a 1, then the number that it represents counts.
>
> - If the bit is a 0, then the number that it represents does not count.
>
> - To convert to binary, the octet number starting from the left to the last is subtracted from the decimal number to be converted to binary number. i.e;
>
>   [decimal number - each octet number]
>
> - If the subtracted value gives a positive number, 1 is indicated as the bit value. But if it gives a negative value, 0 is indicated as the bit value. The decimal number or the value after giving a positive value is used to subtract the next octet number. The same process is repeated till the binary numbers are correct and completed.

Let\'s take a look at few examples to understand this better.

Example 1: Convert 168 to binary number.

Using the 8 bit octet chart,

          128  64  32  16  8  4  2  1

            1   0   1   0  1  0  0  0

_Observe;_

{: .prompt-tip }

> - Using the formula [decimal number - each octet number], [168 - 128 = 40], gives an answer that is a positive value, hence, 1 is indicated.
>
> - [40 - 64 = -24], gives a negative value, hence, 0 is indicated. The 40 is then reused to subtract the next number which is 32.
>
> - [40 - 32 = 8], gives a positive value, 1 is indicated.
>
> - [8 - 16 = -8], gives a negative value, 0 is indicated. -[8 - 8 = 0], gives a positive value, 1 is indicated.
>
> - The rest gives negative values, so 0 is indicated for them.

**Hence, 168 is 10101000 in binary.**

Example 2: Convert 255 to binary

Using the 8 bit chart,

           128  64  32  16  8  4  2  1

             1   1   1   1  1  1  1  1

**Hence, 255 is 1111111 in binary.**

Example 3: Convert 01101101 to decimal

Using the 8 bit chart,

          128  64  32  16  8  4  2  1

            0   1   1   0  1  1  0  1

_Observe again;_

{: .prompt-tip }

> - To convert from binary to decimal, you place the binary bits under each octet chart number, then sum up the octet chart numbers whose bit is 1, and the ones with 0 bits are ignored.
>
> - Therefore, the sum of 64,32,8,4 and 1 gives the decimal number.

**Hence, 01101101 is 109**

Example 4: Convert 10010010

Using the 8 bit chart,

          128  64  32  16  8  4  2  1

            1   0   0   1  0  0  1  0

**Hence, 10010010 is 146**

### Conclusion

Now, you can understand and deal with binary system conversion of IPv4 address and subnet mask. Challenge yourself with other numbers in binary and decimal to perfect your knowledge, as you deal with IP addresses and subnet mask in computers and networks.
