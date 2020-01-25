# DEF

`DEF` defines a function or a subroutine.

## Forms

{% tabs %}
{% tab title="Single line Function" %}
```
DEFFN fnName([arg [, args...]]) = expression
```
{% endtab %}

{% tab title="Multiline Function" %}
```text
DEFFN fnName([arg [, args...])
  REM statements
  RETURN result
ENDFN
```
{% endtab %}

{% tab title="Subroutine" %}
```
DEFSUB subName([arg [, args...]])
  REM Statements
ENDSUB
```
{% endtab %}
{% endtabs %}

## Examples

{% tabs %}
{% tab title="Single line Function" %}
```text
DEFFN double(x) = x * 2
DEFFN textAddr(row, col) = row * 32 + col
```
{% endtab %}

{% tab title="Multiline Function" %}
```
DEF FN upper$(str$)
  DIM t$, ch$, ch
  FOR i = 0 TO LEN(str$)
    ch$ = str$[i]
    ch = ASC(ch$)
    IF ch >= ASC("a") AND ch <= ASC("z") THEN
      ch = ch - 32
    ENDIF
    t$ = t$ + CHR$(ch)
  NEXT i
  RETURN t$
ENDFN
```
{% endtab %}

{% tab title="Subroutine" %}
```
DEFSUB printIntro()
  PRINT "Hello, world!"
ENDSUB
```
{% endtab %}
{% endtabs %}

