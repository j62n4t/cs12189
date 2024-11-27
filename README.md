java c
Data Structures: Huffman Encoder Part 2
November   15, 2024
Last   week   you   wrote code   that   takes a   table of characters and   their   frequencies   to
build a Hu@man encoding.   The purpose of the Hu@man encoding   was to represent a chunk   of text e@iciently by encoding common characters using fewer bits.   This   week   you   will use the code   you   wrote last   week   to encode and decode   text.
You   will   start   by   deﬁning   a   new   class   called   HuffmanConverter   which   will   have   a constructor taking as input a string   which   will be stored in a   variable called contents.
Your   ﬁrst step is   to calculate   the   frequencies of each character including
punctuation and   whitespaces. Each   ASCII character corresponds   to a number between 0   and   255 (inclusive),   which   you   can   get   by   casting   a   character   c   into   an   integer: int   i   =   (int)c.   You   can   then   get   the   character   back   as   c   =   (char)i.   We   will   store   the frequencies of   the characters in an integer array, count, of size 256 such   that   count[(int)c]   = the   count   of   character   c. HuffmanConverter   will   have   a   method public void recordFrequencies()that stores the counts of the characters in contents   in   an   attribute   count. Print   the   table   of   frequencies   you’ve   created.
Second,   you   will   build   a   Hu@man   tree   from   count   using   the   code   you’ve   already written.   Your code should build a heap using count   and   then call   HuffmanTree.createFromHeap.   The   Hu@man   tree   should   be   stored   in   an   attribute huffmanTree. This should occur in a method public void   frequenciesToTree().
Third,   you   will extract a code from the tree.   You   will   want to store the code in a string   array   attribute   called   code   such   that   code[(int)c]   = the   Hu@man   encoding   of   character   c.   This   will   be   done   in   a   method   public   void   treeToCode().   You   will   also need   to   write   a   private   method   private   void   treeToCode(HuffmanNode   t,   String encoding).   This private method recursively calls itself on the children of the Hu@man   node   t, keeping   track   of   its   encoding   encoding; once   it   reaches   a   leaf, it   adds 代 写Data Structures: Huffman Encoder Part 2R
代做程序编程语言the character at that leaf and   the encoding to code. In treeToCode(),   ﬁrst set every   element   of   code   to   the   empty   string   "", then   call   treeToCode   at   the   root   of   the   Hu@man tree. Print   the   code   you   have   created;   this   can   also   be   done   using   a   call   to huffmanTree.printLegend().
Fourth, once   you’ve built code,   you can encode contents into a string of bits in a
method public String   encodeMessage(). Print the encoded message.   Also print the   message   size   in   the   ASCII   encoding   (8 bits   for   each   letter) and   the   Hu@man   encoding.
Finally,   you   will   write   a   method   public   String   decodeMessage(String
encodedStr)to   decode   a   given   bit   string   using   huffmanTree.   To   do   so,   you   will   take   in       one   bit   at   a   time   to   navigate   through   the   huffmanTree   (0 means   go   left, 1 means   go   right).   Once   you reach a leaf,   you should store   the character at   that leaf and return   to   the root of   the Hu@man tree. Call decodeMessage   on   your encoded message and print   the decoded   message,   which should be identical   to   your original message.
We   will   call   the   main   ()   method   of   HuffmanConverter   from   the   command   line,   passing   the path   to a   ﬁle of   text.   To recap,   the output should be:
-          the list of characters and   their   frequencies
-            the   Hu@man   encodings
-          the encoded message
-          the number of bits needed   to encode   your message in a Hu@man encoding   vs   using ASCII
-          the decoding of   your encoded message (which should be   the same as   the initial   message)
You are provided a ﬁle   with a template of HuffmanConverter   with code to import      a text ﬁle.   You are also provided   with two example input and output ﬁles.   The inputs are two   love poems   taken   totally randomly   from http://www.lovepoemsandquotes.com. Feel   free to   try out   your own inputs   to   test   your program.
Please submit   your completed [email   protected] ﬁle on Brightspace.   You   should not need   to make changes   to any of   the   ﬁles   from part 1 in order   to do   this assignment.





         
加QQ：99515681  WX：codinghelp  Email: 99515681@qq.com
