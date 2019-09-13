---
title: Оператор преобразования в строку (#)
ms.date: 08/29/2019
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
ms.openlocfilehash: 5a1b43198e59bc1e69cdf1b56db56be75719fe46
ms.sourcegitcommit: 6e1c1822e7bcf3d2ef23eb8fac6465f88743facf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/03/2019
ms.locfileid: "70216551"
---
# <a name="stringizing-operator-"></a>Оператор преобразования в строку (#)

Оператор Number-Sign или "строковый" ( **#** ) преобразует параметры макроса в строковые литералы без расширения определения параметра. Он используется только с макросами, принимающими аргументы. Если он стоит перед формальным параметром в определении макроса, то фактический аргумент, передаваемый вызовом макроса, заключается в кавычки и обрабатывается как строковый литерал. Далее этим строковым литералом заменяется каждое сочетание строкового оператора с формальным параметром, которое встречается в определении макроса.

> [!NOTE]
> Расширение Microsoft C (версии 6.0 и более ранних) для стандарта ANSI C, которое ранее развертывало формальные аргументы макросов в строковых литералах и символьных константах, больше не поддерживается. Код, который использовался для этого расширения, должен быть перезаписан с помощью **#** оператора строковый ().

Пробел, предшествующий первому маркеру и следующий за последним маркером фактического аргумента, игнорируется. Все пробелы между токенами в фактическом аргументе сокращаются в полученном строковом литерале до одиночных пробелов. Таким же, если комментарий находится между двумя маркерами в фактическом аргументе, он сокращается до одного пробела. Результирующий строковый литерал автоматически объединяется с любыми соседними строковыми литералами, разделенными только пробелом.

Кроме того, если символ, содержащийся в аргументе, обычно требует escape-последовательности при использовании в строковом литерале, например кавычки`"`() или обратная косая черта (`\`), то необходимая escape-обратная коса автоматически вставляется перед символом.

Оператор Microsoft C++ строковый работает неправильно, если он используется со строками, включающими escape-последовательности. В этом случае компилятор создает [ошибку компилятора C2017](../error-messages/compiler-errors-1/compiler-error-c2017.md).

## <a name="examples"></a>Примеры

В следующем примере показано определение макроса, включающее оператор строковый, и функция Main, которая вызывает макрос:

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

`stringer` Макросы развертываются во время предварительной обработки, создавая следующий код:

```cpp
int main() {
   printf_s( "In quotes in the printf function call" "\n" );
   printf_s( "\"In quotes when printed to the screen\"" "\n" );
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
