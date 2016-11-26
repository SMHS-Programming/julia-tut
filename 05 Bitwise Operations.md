# Bitwise Operations
Most programming languages (Julia included) use bits to represent numbers. Each bit is represented by `0`s and `1`s, and a number represented by 32 bits is called a 32-bit number. For example:

```
0000000000000000000000000000000000000000000000000000000010011000
```
represents a 64-bit integer 152. To view the bits of a number, use the `bits` function:

```
bits(152)
```
The leftmost bit determines the sign of the number: `0` for positive, `1` for negative. This bit is called the **sign bit**.

The following bitwise operators only work on integers by default.

## AND `&`
Takes 2 integers and applies the following truth table:

``|1|0
---|---|---|
**1** |1|0
**0** |0|0

For example:

```
152 & 23

0000000000000000000000000000000000000000000000000000000010011000
0000000000000000000000000000000000000000000000000000000001111011
Apply AND:
0000000000000000000000000000000000000000000000000000000000011000
```

## OR `|`
Takes 2 integers and applies the following truth table:

``|1|0
---|---|---|
**1** |1|1
**0** |1|0

For example:

```
152 | 123

0000000000000000000000000000000000000000000000000000000010011000
0000000000000000000000000000000000000000000000000000000001111011
Apply OR:
0000000000000000000000000000000000000000000000000000000011111011
```

## XOR `$`
Takes 2 integers and applies the following truth table:

``|1|0
---|---|---|
**1** |0|1
**0** |1|0

For example:

```
152 $ 123

0000000000000000000000000000000000000000000000000000000010011000
0000000000000000000000000000000000000000000000000000000001111011
Apply XOR:
0000000000000000000000000000000000000000000000000000000011100011
```

## NOT `~`
Takes each bit and turns 1 to 0 / vice versa.

For example:

```
~ 152
0000000000000000000000000000000000000000000000000000000010011000
Apply NOT:
1111111111111111111111111111111111111111111111111111111101100111
```

## Shifts `<<` `>>` `>>>`
These shift bits right or left by a certain amount and discard any hanging bits.

Left shift:

```
152 << 2
0000000000000000000000000000000000000000000000000000000010011000
Apply left shift by 2:
0000000000000000000000000000000000000000000000000000001001100000
```

Arithmetic right shift:

```
-1 >> 2
1111111111111111111111111111111111111111111111111111111111111111
Apply arithmetic right shift by 2:
1111111111111111111111111111111111111111111111111111111111111111
```

Logical right shift:

```
-1 >>> 2
1111111111111111111111111111111111111111111111111111111111111111
Apply logical right shift by 2:
0011111111111111111111111111111111111111111111111111111111111111
```

Notice the difference between arithmetic and logical right shift. Arithmetic right shift preserves the sign bit, but logical right shift does not. Logical right shift pads the left side of the bits with `0`s.