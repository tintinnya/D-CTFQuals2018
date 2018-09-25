# Multiple Flags (Junior - 1 pcts.) 

>Look, flags everywhere!
>
>![semaphore flag](https://github.com/tintinnya/D-CTFQuals2018/raw/master/multiple-flags/multiple-flags.png)

## Solution

The first thing came to my mind when I saw the image is: boyscout's semaphore flags! I remember when I was elementary school, the Boy Scout's ~~encryption~~ encoding using two flags. Google gave me interesting [link](https://www.123rf.com/photo_13594743_semaphore-flag-positions-for-the-alphabet.html) to teach you on how to decode each flags' position.

The interesting part is there is a signal to switch gear from numeral to alphabet or vice versa. Otherwise, it would not be able to understand, and it'll give you wrong flag.

Citing the flag position from above link, I decoded each line as follow

```
j/LTR	d/4	c/3	t	f/6	s	p
e/5	c/3	i/9	a/1	l	f	l
a/1	g/7	NUM	k/0	k/0	j/LTR	a/1
a/1	NUM	k/0	k/0	j/LTR	a/1	a/1
NUM	k/0	k/0	i/9	i/9	a/1	c/3
c/3	g/7	j/LTR	d/4	c/3	t	f
```

At the beginning, I can't understand the flag in row 3 col 3. But apparently, it was the signal to sending numeral instead of letters. And it became make sense when J is interpreted as signal to send letters instead of numeral signal. Hence, the decoding became:

```
LET	d	c	t	f	s	p
e	c	i	a	l	f	l
a	g	NUM	0	0	LTR	a
a	NUM	0	0	LTR	a	a
NUM	0	0	9	9	1	3
3	7	LTR	d	c	t	f
```
or
```
dctfspecialflag00aa00aa00991337dctf
```

