---
title: Строковый оператор (#) | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- '#'
dev_langs:
- C++
helpviewer_keywords:
- preprocessor, operators
- arguments [C++], converting to strings
- stringizing operator
- preprocessor
- string literals, converting macro parameters to
- macros [C++], converting parameters to strings
- '# preprocessor operator'
ms.assetid: 1175dd19-4538-43b3-ad97-a008ab80e7b1
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 7891b03fe80b5ad91ad52cf4577d237350d4584c
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/07/2018
---
# <a name="stringizing-operator-"></a>Строковый оператор (#)
Знак решетки, или «строковый» оператор (**#**) преобразует параметры макроса в строковые литералы без развертывания определения параметра. Он используется только с макросами, которые принимают аргументы. Если он стоит перед формальным параметром в определении макроса, то фактический аргумент, передаваемый вызовом макроса, заключается в кавычки и обрабатывается как строковый литерал. Далее этим строковым литералом заменяется каждое сочетание строкового оператора с формальным параметром, которое встречается в определении макроса.  
  
> [!NOTE]
>  Расширение Microsoft C (версии 6.0 и более ранних) для стандарта ANSI C, которое ранее развертывало формальные аргументы макросов в строковых литералах и символьных константах, больше не поддерживается. Код, в котором использовалось это расширение, необходимо переписать с использованием строкового (**#**) оператор.  
  
Пробелы, находящиеся перед первым токеном и после последнего токена фактического аргумента, игнорируются. Все пробелы между токенами в фактическом аргументе сокращаются в полученном строковом литерале до одиночных пробелов. Таким образом, если между двумя токенами в фактическом аргументе находится комментарий, он сокращается до одиночного пробела. Для полученного строкового литерала автоматически выполняется конкатенация со всеми соседними строковыми литералами, от которых он отделяется только пробелами.  
  
Далее, если символ, содержащийся в аргументе обычно требует escape-последовательности при использовании в строковом литерале (например, знак кавычки (**»**) или обратная косая черта (**\\**) символ), Перед этим символом автоматически подставляется косая.  
  
Visual C++ строковый оператор работать некорректно при использовании со строками, которые включают escape-последовательности. В этом случае компилятор создает [Ошибка компилятора C2017](../error-messages/compiler-errors-1/compiler-error-c2017.md).  
  
## <a name="example"></a>Пример  
В приведенном ниже примере показано определение макроса, в котором содержится строковый оператор, а также функция main, которая вызывает этот макрос.  
  
Такие вызовы будут развернуты во время предварительной работки. В результате будет создан следующий код:  
  
```cpp  
int main() {  
   printf_s( "In quotes in the printf function call\n" "\n" );  
   printf_s( "\"In quotes when printed to the screen\"\n" "\n" );  
   printf_s( "\"This: \\\" prints an escaped double quote\"" "\n" );  
}  
```  
  
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
  
```Output  
In quotes in the printf function call  
"In quotes when printed to the screen"  
"This: \"  prints an escaped double quote"  
```  
  
## <a name="example"></a>Пример  
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