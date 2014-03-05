---
layout: post
author: katielmeyer
title: Pipes and filters
date: 2014-03-05
---

---
layout: post
author: katielmeyer
title: Pipes and filters
date: 2014-03-05
---

I'm not sure why, but the default behavior of the sort program in my nitrous CL is to sort the items in descending order. So when I sort the lengths
file's contents and reveal the first line with head -1, I get:

```

107 total

```

Instead of the sample output in the instructions:

```

9 methane.pdb

```

I can only get that result by adding the reverse option (-r) or the numerical option (-n):

```

$ sort -r lengths | head -1
$ 9 methane.pdb

```

### Challenges

1. Adding -n to the sort command tells the program to sort the items by number value.

2. They're both ways to tell the program where to get its input. When you don't specify with a <, 
the returned output gives both the wordcount & file name

3. In order to be able to remove each repetitive line from its input, it would need to be able to store each unique item and compare
each new line to that master list of items it's already found. For very long items or very long lists of items, that take a very long time. You 
could be sure to remove all duplicate items by first sorting the file alphabetically, then running uniq:

```

sort salmon.txt | uniq

```

4. The cat command just prints out the contents of one or more files. Since we only have one file in this case, I don't think it's really
necessary here. Head takes the first 5 lines of that file:

```

2012-11-05,deer
2012-11-05,rabbit
2012-11-05,raccoon
2012-11-06,rabbit
2012-11-06,deer

```

Then tail takes the last 3 lines of those 5:

```

2012-11-05,raccoon
2012-11-06,rabbit
2012-11-06,deer

```

Finally, those lines are sorted in reverse order and the output goes to final.txt.

```

2012-11-06,rabbit  
2012-11-06,deer                                                                                                                                        
2012-11-05,raccoon

```

5. We can find out the unique animals in this list by adding sort & uniq to the command.

```

cut -d , -f 2 animals.txt | sort | uniq

```
