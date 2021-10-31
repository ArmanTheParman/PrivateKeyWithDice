# PrivateKeyWithDice
Make your own private key with dice

A template based on my guide https://armantheparman.com/bitcoin-seed-with-dice/ for creating your own seed phrase for a Bitcoin BIP 39 wallet

Instructions:

Print out the template provided (template.png)

Create a RANDOM sequence of 256 binary digits (0s and 1s) and fill them into the top row of for each word in the template.
You can use dice to gernerate binary digits (as described in the guide), or even flip a coin 256 times (slow!)

256 digits will fill up the page except the last 8 digits of the 24th word.
The remaining EIGHT digits are reserved for the checksum.
On a Mac or Linux machine, run the following command, where <binary_sequence> is the sequence of 256 binary digits you created in the previous steps (no spaces):

echo <binary_sequence> | shasum -a 256 -0

Convert each of the first TWO characters of the output from this command from hexadecimal to decimal, and then from decimal to binary. (Do it by hand, not computer because this data is private). Eg if you had a hash that started with "ff..." then that would give you 15 & 15 in decimal. That is 1111 & 1111 in binary.

Combine the two binary numbers. In the example above that would give 8 digits: 11111111, which is the checksum.

Record your checksum to complete the template.

For each word box in the template, there is a decimal row. If there is a '1' in the above binary row, record down the decimal number below. For example if the binary above was 10000000001, then below the 1 on the left you'd write 1024, and the 1 on the right you would write 1.

Then total the decimals. For the above example, the total would bey 1024+1=1025

For each word, look up the word list provided to find the corresponding number.

You could look up the original source in github as well, but note that the list on github begins with "1" not "0" so you need to offset the word you choose. Eg a decimal of '0' does not exist on the github list and you'll have to choose word #1 (abandon). On the list provided, abandon is labelled word#0 so it's easier to use this list.

When you complete the form, you have a private seed phrase whih can generate a wallet.
Be aware it is not safe to type this in to a computer. Use a hardware wallet or an air-gapped computer.
Learn more about safe private key practices at armantheparman.com
