---
title: Анализ аргументов командной строки C++ | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- quotation marks, command-line arguments
- double quotation marks
- command line [C++], parsing
- parsing, command-line arguments
- startup code, parsing command-line arguments
ms.assetid: e634e733-ac2f-4298-abe2-7e9288c94951
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: eca85baea71052525d70c90ac521ef5fa95a5118
ms.sourcegitcommit: 2b9e8af9b7138f502ffcba64e2721f7ef52af23b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/01/2018
ms.locfileid: "39409209"
---
# <a name="parsing-c-command-line-arguments"></a>Анализ аргументов командной строки C++
**Блок, относящийся только к системам Microsoft**  
  
 В коде запуска Microsoft C/C++ используются следующие правила при обработке аргументов, вводимых в командной строке операционной системы.  
  
-   Аргументы разделяются пробелами (пробел или табуляция).  
  
-   Символ каретки (^) не воспринимается как escape-символ или разделитель. Этот символ полностью обрабатывается синтаксическим анализатором командной строки в операционной системе, прежде чем передается в массив `argv` программы.  
  
-   Строка, заключенная в двойные кавычки (»*строка*«) интерпретируется как один аргумент, независимо от пробельных, содержащихся в. Строку в кавычках можно встроить в аргумент.  
  
-   Символ двойной кавычки после обратной косой черты (\\") обрабатывается как символ двойной кавычки литерала (").  
  
-   Символы обратной косой черты обрабатываются буквально, если только им не предшествует двойная кавычка.  
  
-   Если после четного числа символов обратной косой черты стоит двойная кавычка, в массив `argv` помещается по одному символу обратной косой черты (\) для каждой пары символов обратной косой черты (\\), а двойная кавычка (") обрабатывается как разделитель строки.  
  
-   Если после нечетного числа символов обратной косой черты стоит двойная кавычка, в массив `argv` помещается по одному символу обратной косой черты (\) для каждой пары символов обратной косой черты (\\), а символ двойной кавычки с оставшимся символом обратной косой черты интерпретируется как escape-последовательность, в результате чего в массив `argv` помещается литеральный символ двойной кавычки (").  
  
## <a name="example"></a>Пример  
 В следующем примере программы показана передача аргументов командной строки:  
  
```cpp 
// command_line_arguments.cpp  
// compile with: /EHsc  
#include <iostream>  
  
using namespace std;  
int main( int argc,      // Number of strings in array argv  
          char *argv[],   // Array of command-line argument strings  
          char *envp[] )  // Array of environment variable strings  
{  
    int count;  
  
    // Display each command-line argument.  
    cout << "\nCommand-line arguments:\n";  
    for( count = 0; count < argc; count++ )  
         cout << "  argv[" << count << "]   "  
                << argv[count] << "\n";  
}  
```  
  
 В следующей таблице показаны примеры входных данных и ожидаемые выходные данные, иллюстрирующие применение правил из приведенного выше списка.  
  
### <a name="results-of-parsing-command-lines"></a>Результаты синтаксического анализа командной строки  
  
|Данные в командной строке|argv[1]|argv[2]|argv[3]|  
|-------------------------|---------------|---------------|---------------|  
|`"abc" d e`|`abc`|`d`|`e`|  
|`a\\b d"e f"g h`|`a\\b`|`de fg`|`h`|  
|`a\\\"b c d`|`a\"b`|`c`|`d`|  
|`a\\\\"b c" d e`|`a\\b c`|`d`|`e`|  
  
**Завершение блока, относящегося только к системам Майкрософт**  
  
## <a name="see-also"></a>См. также  
 [Функция main: запуск программы](../cpp/main-program-startup.md)