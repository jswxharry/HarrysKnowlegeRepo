
Regular Expressions, abbreviated as Regex or Regexp, are a string of characters created within the framework of Regex syntax rules. You can easily manage your data with Regex, which uses commands like finding, matching, and editing.

# Refereences:
- [Regex Lean](https://regexlearn.com) is a very good web site can help you to learn Regex(**Highly recommended to take the online courses**) and also can just check the [Regex Lean Cheetsheet](https://regexlearn.com/cheatsheet) or [My Cheetsheet](#my-cheetsheet) below.
- [Java Regex Chinese Simplified](https://cloud.tencent.com/developer/information/java%E4%B8%AD%E7%9A%84regular-expression)


# My Cheetsheet

## Character Matching
To match or not, below are the Regex expression examples.

| Sign | Desc | Example Text input | Expression example |Example output|
|------|------|--------------------|--------------------|--------------|
|abc   |Direct type the word to be matched| abcdefabc|abc|abcabc|
|.     | Dot: match any character| abcde|.|abced|
|[abc] | Character Set: If one of the characters in a word can be various characters, we write it in square brackets [] with all alternative characters.| bar ber bir| b[ae]r| bar ber|
|[^abc]| Negated Character Sets: match all words <ins>**except**</ins> the abc, write after the ^(caret) sign| bar ber bir| b[^i]r| bar ber|
|[a-z]| Letter Range:find the letter in specific range(inclusive), case sensitive|abcdefg|[ad-g]|adefg|
|[0-9]| Number Range:find the number in specific range(inclusive)|123456789|[3-6]|3456|

## Repetitions
Some special characters are used to specify how many times a character will be repeated in the text. These special characters are the plus +, the asterisk *, and the question mark ?. Every repetitions are write <ins>**after**</ins> the character
| Sign | Desc | Example Text input | Expression example |Example output|
|------|------|--------------------|--------------------|--------------|
|*     |put an asterisk * after a character to indicate that the character may either <ins>**not match at all**</ins> or can <ins>**match many times**</ins>.| br beer beeer baer| be*r|br beer beeer|
|+     |put an Plus + after a character to indicate that the character may <ins>**match many times**</ins> but must at least match <ins>**once**</ins>, compare with *| br beer beeer baer| be+r|beer beeer|
|?     |put a question mark ? a character to indicate that the character maybe optional| br ber beer beeer baer| be?e?r| br ber beer|
|{n}   | write curly braces {n} after a character indicate how many times - n we want it to occur| br ber beer beeer|be{2}r| beer|
|{n,}   | write curly braces with n + comma {n,} after a character indicate how many times - n <ins>**at least**</ins> we want it to occur| br ber beer beeer|be{2,}r| beer beeer|
|{n1,n2}   | write  {n1,n2} after a character indicate times range - n1,n2 (inclusive) the character can occur| br ber beer beeer beeer|be{2,3}r| beer beeer|

Combinded above two, some example to refersh:
|Task |Example Text Input | Expression | Example ouput|
|-----|-------------------|------------|--------------|
|Find texts containing at least 2 and at most 4 numbers side by side.|Release 10/9/2021|[0-9]{2,4}|10 2021|

## Boundary Matchers

About where in the string the match was taking place. Referecing from [Boundary Matchers](https://docs.oracle.com/javase/tutorial/essential/regex/bounds.html), below just listed some important others can read more in the reference link.

| Sign | Desc | Example Text input | Expression example |Example output|
|------|------|--------------------|--------------------|--------------|
|^|To find only characters at the beginning of a line, prefix this expression with the ^ sign|1. 3 eggs, beaten|^[0-9]| 1|
|$|Dollar Sign, place it after the expression which only select the one in the end of the line|https://domain.com/what-is-html.html|html$|html|
|\b|A word boundary|The dog plays in the yard.|\bdog\b|dog|
|\B|A non-word boundary(very interesting definition, detail suggset to read [here](https://blog.csdn.net/nicajonh/article/details/78815869))|The dog plays in the yard.|\Bla\B|la|



## Others
| Sign | Desc | Example Text input | Expression example |Example output|
|------|------|--------------------|--------------------|--------------|
|()    |Parentheses can make a expression as a group which can be referenced later| ha-ha-ha| (ha) | ha ha ha|
|\n    |to reference the predefined group can use \n, n stands for which group. i.e group 1 then \1|ha-ha-ha|(ha)-\1-\1|ha-ha-ha|
|(:?)  |Non-capturing Grouping, group an expression and ensure that it is not captured by references. can access by \n| ha-ha,haa-haa | (?:ha)-ha,(haa)-\1|ha-ha,haa-haa|
|\||Pipe Character allows to specify all possible statements, Alternatives are at the expression level. For example, the following expression would select both cat and rat. Add another pipe sign \| to the end of the expression and type dog so that all words are selected.|cat rat dog| (c\|r)at\|dog| cat rat dog|
|\w|Word Character \w is used to find letters, numbers and underscore characters.|abcABC123 _.:!?|\w|abcABC123_|
|\W|Except Word Character \W is used to find characters other than letters, numbers, and underscores.|abcABC123 _.:!?|\W| .:!?|
|\d|Number Character, used to find only number characters.|abcABC123 _.:!?|\d|123|
|\D|Except Number Character, used to find non-numeric characters.|abcABC123 _.:!?|\D|abcABC _.:!?|
|\s|Space character, find the space|abcABC123 _.:!?|\s| |
|\S|Except Space character, find the none-space character|abcABC123 _.:!?|\S|abcABC123_.:!?|

## Lookarounds
select the text before or after specific pattern
| Sign | Desc | Example Text input | Expression example |Example output|
|------|------|--------------------|--------------------|--------------|
|(?=)  | Positive Lookahead, to select only the numerical values that before the specific pattern - "PM", we need to write the positive look-ahead expression (?=) after our expression.| Date: 4 Aug 3PM|\d+(?=PM)|3|
|(?!)  | Negative Lookahead, to select only the numerical values that <ins>**NOT**</ins> not before specific pattern - "PM" , we need to write the positive look-ahead expression (?=) after our expression.| Date: 4 Aug 3PM|\d+(?!PM)|4|
|(?<=) | Positive Lookbehind, to select the value after a specific pattern, we need to write the look-behind expression (?<=) before the expression.|Product Code: 1064 Price: $5|(?<=\\$)\d+|5|
|(?<!) | Negative Lookbehind, to select the value <ins>**NOT**</ins> after a specific pattern, we need to write the look-behind expression (?<=) before the expression.|Product Code: 1064 Price: $5|(?<!\\$)\d+|1064|

## Flags
Flags change the output of the expression. Flags determine whether the typed expression treats text as separate lines, is case sensitive, or finds all matches.


| Sign | Desc | Example Text input | Expression example |Example output|
|------|------|--------------------|--------------------|--------------|
|/g    |The global flag causes the expression to select <ins>**all**</ins> matches. If not used it will only select the **first** match|domain.com, test.com, site.com|\w+\.com/g|domain.com test.com site.com|
|/m    |Regex sees all text as one line. But we use the multiline flag to handle each line separately.|domain.com<br>test.com<br>site.com|\w+\.com$/gm|domain.com<br>test.com<br>site.com|
|/i    |Remove the case-sensitivity of the expression we have written.|DOMAIN.COM<br>TEST.COM<br>SITE.COM|\w+\.com$/gmi|DOMAIN.COM<br>TEST.COM<br>SITE.COM|

## Greedy Matching
Regex does a greedy match by default. This means that the matching will be as long as possible. Check out the example below. It refers to any match that ends in r and can be any character preceded by it. But it does not stop at the first match.

| Example Text input | Expression example |Example output|
|--------------------|--------------------|--------------|
|ber beer beeer beeeer|.*r|ber beer beeer beeeer|

## Lazy Matching
Lazy matching, unlike greedy matching, stops at the first matching. For example, in the example below, add a ? after * to find the first match that ends with the letter r and is preceded by any character. It means that this match will stop at the first letter r.

| Example Text input | Expression example |Example output|
|--------------------|--------------------|--------------|
|ber beer beeer beeeer|.*?r|ber|

# Use Regular Expression in Java

## Basic matching:

``` Java
import java.util.regex.Pattern;
import java.util.regex.Matcher;

public class RegexExample {
    public static void main(String[] args) {
        String text = "Hello, my email is example@domain.com";
        String patternString = "\\b[A-Za-z0-9._%+-]+@[A-Za-z0-9.-]+\\.[A-Za-z]{2,}\\b";
        
        Pattern pattern = Pattern.compile(patternString);
        Matcher matcher = pattern.matcher(text);
        
        if (matcher.find()) {
            System.out.println("Found email: " + matcher.group());
        } else {
            System.out.println("No email found");
        }
    }
}
```

## Get by groups:
``` Java
String text = "John Doe, 30 years old";
Pattern pattern = Pattern.compile("(\\w+)\\s+(\\w+),\\s+(\\d+)\\s+years old");
Matcher matcher = pattern.matcher(text);

if (matcher.matches()) {
    System.out.println("First name: " + matcher.group(1));
    System.out.println("Last name: " + matcher.group(2));
    System.out.println("Age: " + matcher.group(3));
}
```

## String Replace

``` Java
String text = "The quick brown fox jumps over the lazy dog";
String replaced = text.replaceAll("(?i)fox", "cat");
System.out.println(replaced);  // The quick brown cat jumps over the lazy dog
```

## String Split

``` Java
String text = "apple,orange,banana,grape";
String[] fruits = text.split(",");  // split will take the regex input
for (String fruit : fruits) {
    System.out.println(fruit);
}
```

## How to use Flags in Java
The so called: *embedded flag expression*, refering to [Java Tutorials - Pattern with flags](https://docs.oracle.com/javase/tutorial/essential/regex/pattern.html)

Please also reference to [Flags](#flags), read more details in Java Pattern.java source code
``` Java
// /i (?i)
Pattern pattern = Pattern.compile(patternString, Pattern.CASE_INSENSITIVE);

// /m  (?m)
Pattern pattern = Pattern.compile(patternString, Pattern.MULTILINE);

// (?s)  single line mode

// do enable multiple flags using Pattern.compile
final int flags = Pattern.CASE_INSENSITIVE | Pattern.UNICODE_CASE;
Pattern pattern = Pattern.compile("aa", flags);

// or just to do embedded flags
Pattern pattern = Pattern.compile("(?iu)aa", flags);

```
