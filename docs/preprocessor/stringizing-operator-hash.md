---
title: Строковый оператор (#)
ms.date: 11/04/2016
f1_keywords:
- '#'
helpviewer_keywords:
- preprocessor, operators
- arguments [C++], converting to strings
- stringizing operator
- preprocessor
- string literals, converting macro parameters to
- macros [C++], converting parameters to strings
- '# preprocessor operator'
ms.assetid: 1175dd19-4538-43b3-ad97-a008ab80e7b1
ms.openlocfilehash: 720817b34326d822ef797351655e4ace907e4baf
ms.sourcegitcommit: 20a1356193fbe0ddd1002e798b952917eafc3439
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/30/2019
ms.locfileid: "68661630"
---
# <a name="stringizing-operator-"></a>Строковый оператор (#)

Оператор Number-Sign или "строковый" ( **#** ) преобразует параметры макроса в строковые литералы без расширения определения параметра. Он используется только с макросами, которые принимают аргументы. Если он стоит перед формальным параметром в определении макроса, то фактический аргумент, передаваемый вызовом макроса, заключается в кавычки и обрабатывается как строковый литерал. Далее этим строковым литералом заменяется каждое сочетание строкового оператора с формальным параметром, которое встречается в определении макроса.

> [!NOTE]
> Расширение Microsoft C (версии 6.0 и более ранних) для стандарта ANSI C, которое ранее развертывало формальные аргументы макросов в строковых литералах и символьных константах, больше не поддерживается. Код, который использовался для этого расширения, должен быть перезаписан с помощью **#** оператора строковый ().

Пробелы, находящиеся перед первым токеном и после последнего токена фактического аргумента, игнорируются. Все пробелы между токенами в фактическом аргументе сокращаются в полученном строковом литерале до одиночных пробелов. Таким образом, если между двумя токенами в фактическом аргументе находится комментарий, он сокращается до одиночного пробела. Для полученного строкового литерала автоматически выполняется конкатенация со всеми соседними строковыми литералами, от которых он отделяется только пробелами.

Кроме того, если символ, содержащийся в аргументе, обычно требует escape-последовательности при использовании в строковом литерале (например, знак кавычек ( **"** ) или **\\** обратная косая черта ()), то обязательная обратная косая черта вставляется автоматически перед символом.

Оператор Visual C++ строковый работает неправильно, если он используется со строками, включающими escape-последовательности. В этом случае компилятор создает [ошибку компилятора C2017](../error-messages/compiler-errors-1/compiler-error-c2017.md).

## <a name="examples"></a>Примеры

В приведенном ниже примере показано определение макроса, в котором содержится строковый оператор, а также функция main, которая вызывает этот макрос.

```cpp
// stringizer.cpp
#include <stdio.h>
#define stringer( x ) printf_s( #x "\n" )
int main() {
   stringer( In quotes in the printf function call );
   stringer( "In quotes when printed to the screen" );
   stringer( "This: \"  prints an escaped double quote" );
}
```

Такие вызовы будут развернуты во время предварительной работки. В результате будет создан следующий код:

```cpp
int main() {
   printf_s( "In quotes in the printf function call\n" "\n" );
   printf_s( "\"In quotes when printed to the screen\"\n" "\n" );
   printf_s( "\"This: \\\" prints an escaped double quote\"" "\n" );
}
```

```Output
In quotes in the printf function call
"In quotes when printed to the screen"
"This: \"  prints an escaped double quote"
```

В следующем примере показано, как развернуть параметр макроса:

```cpp
// stringizer_2.cpp
// compile with: /E
#define F abc
#define B def
#define FB(arg) #arg
#define FB1(arg) FB(arg)
FB(F B)
FB1(F B)
```

## <a name="see-also"></a>См. также

[Операторы препроцессора](../preprocessor/preprocessor-operators.md)
