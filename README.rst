A Danish diceware word list
===========================

The words are taken from a `list of the 5000 most used Danish words`_ based on
opensubtitles.org.

.. _`list of the 5000 most used Danish words`:
   http://en.wiktionary.org/wiki/Wiktionary:Frequency_lists/Danish_wordlist


What is it for?
---------------

Generating good and reasonably memorizable passwords. Or, well, let us call them
passphrases.



How to use it?
--------------

1. Find a honest dice.
2. Decide how strong the passphrase needs to be. For every word you add, you add
   just over 10.3 bits to the passphrase strength. So if you need 80 bit
   passphrase strength, you need a passphrase of 8 words.
3. Roll the dice 4 times and look-up the number sequence in
   ``diceware.wordlist-danish.txt``. This word is the first word in your
   passphrase.
4. Repeat until you have collected enough words for your desired passphrase
   strength.


Notice ...
----------

Please notice that you lower the strength if you:

* Interchange words for the passphrase to make more sense.
* Change one word for the passphrase to make more sense.

Generally, you lower the strength if you change the passphrase to make more
sense because everything that increases "meaning" will decrease the independence
between words in your passphrase, and if they are dependent, the entropy is
lowered.

How much? I cannot know.

However, you can increase the strength by:

* Upper casing some letters.
* Replacing some letters by numbers.
* Replacing some letters by symbols.

But be extraordinarily careful when you calculate the increased strength since
replacing e.g. ``s`` by ``5`` does not add as much strength as you might think.
`Obligatory link`_.

.. _`Obligatory link`: http://xkcd.com/936

A fine strategy would be to separate the words by

1. space
2. ``.``
3. ``,``
4. ``-``
5. ``!``
6. ``:``

Toss a dice once for each word you add (except the last) and choose the
separator according to the eyes of the dice. For each time you do this, you add
2.5 bits. So by doing this, you need just 6 words to get almost 75 bit, or 7
words to get 87 bit.


Some questions I asked myself
-----------------------------

   Why didn't you include numbers and symbols in the word list? That would make
   it even harder for brute-forcing or when an attacker does not expect you to
   use the word list.

If I were an attacker, I would only spend some time on each strategy
(brute-forcing, dictionary attach from different word lists etc.). Thus, an
attacker will succeed in using the correct word list way before he would succeed
in brute-forcing, so protecting for the attackers worst-case scenario does not
increase the security. Rather, it makes the passphrase harder to type,
especially if you happen to type your passphrase on different keyboard layouts.

To calculate the passphrase strength you must assume that an attacker knows the
exact conditions under which your passphrase is constructed. Even if your usual
dice has a little skewness that favour larger numbers over smaller (because your
dice has less material on the side of the larger numbers if the dots are holes;
than you damned gravity). Or if you have a lucky number that you prefer to have
upside before tossing. Et cetera.  But, of course not what exact number sequence
you tossed; the conditions, not what happened.

Now, put away that tin foil hat again.


    Why only 1296 words? In the real diceware list (and Beale's) there are 7776.

I am lazy. I didn't bother to find more words. Looking through the word list to
remove offensive words, remove non-Danish names etc. actually took me more than
an hour. By having a list six times longer would require me to spend six times
as much time on sanitising the list. Sorry, add a word more to your passphrase.
Also, you can count on each word to contribute ~10 bits to your strength. Nice
number to remember; better than 12.9 (which every word of the original diceware
word list contributes).


Credits
-------

http://www.diceware.com
