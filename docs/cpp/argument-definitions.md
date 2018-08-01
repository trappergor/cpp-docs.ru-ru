---
title: Определения аргументов | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- envp argument
- main function, arguments
- arguments [C++], for main function
- argv argument
- argc argument
ms.assetid: 6148cbf3-ebe8-44f2-b277-de4b723991c7
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 044c5df5ae0a51912893ccf306a5c93afceb7ab3
ms.sourcegitcommit: 2b9e8af9b7138f502ffcba64e2721f7ef52af23b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/01/2018
ms.locfileid: "39407592"
---
# <a name="argument-definitions"></a>Определения аргументов
Аргументы в прототипе  
  
```cpp 
int main( int argc, char* argv[], char* envp[]);
int wmain( int argc, wchar_t* argv[], wchar_t* envp[]);  
```  
  
 позволяют удобно выполнять синтаксический разбор аргументов в командной строке и дополнительно осуществлять доступ к переменным среды. Используются следующие определения аргументов.  
  
 *argc*  
 Целое число, содержащее количество аргументов, передаваемых в *argv*. *Argc* параметр всегда будет больше или равно 1.  
  
 *argv*  
 Массив завершающихся null строк, представляющих введенные пользователем программы аргументы командной строки. По соглашению `argv` **[0]** — это команда, с помощью которой вызывается программа, `argv` **[1]** — первый аргумент командной строки и т. д., пока `argv`  **[**`argc`**]**, который всегда имеет значение NULL. См. в разделе [Настройка обработки командной строки](../cpp/customizing-cpp-command-line-processing.md) сведения о подавлении обработки в командной строке.  
  
 Первый аргумент командной строки — всегда `argv` **[1]** и последний из них `argv` **[** `argc` - 1 **]**.  
  
> [!NOTE]
>  По соглашению параметр `argv`**[0]** содержит команду, которая использовалась для вызова программы.  Тем не менее, можно инициализировать с помощью процесса [CreateProcess](http://msdn.microsoft.com/library/windows/desktop/ms683197) и при использовании первого и второго аргумента (*lpApplicationName* и *lpCommandLine*), `argv` **[0]** не может быть исполняемый файл, используйте [GetModuleFileName](http://msdn.microsoft.com/library/windows/desktop/ms683197) для получения его полный путь и имя исполняемого файла.  
  
## <a name="microsoft-specific"></a>Блок, относящийся только к системам Microsoft  
 *envp*  
 *Envp* массив, являющийся общее расширение во многих системах UNIX, используется в Microsoft C++. Это массив строк, представляющих переменные, заданные в среде пользователя. Этот массив завершается записью NULL. Его можно объявить как массив указателей на **char (char** \*envp []**)** или как указатель на указатели на **char (char** \* \* envp **)**. Если программа использует `wmain` вместо `main`, использовать `wchar_t` данных вместо типа **char**. Блок среды, передаваемый в `main` и `wmain` является «зафиксированной» копией текущей среды. При изменении среды через вызов `putenv` или `_wputenv`, текущая среда (возвращенная `getenv` / `_wgetenv` и `_environ` /  `_wenviron` переменной) будет Изменение, но блок, на который указывает envp не изменится. См. в разделе [Настройка обработки командной строки](../cpp/customizing-cpp-command-line-processing.md) сведения о подавлении обработки в среде. Этот аргумент совместим с ANSI в C, но не в C++.  
  
**Завершение блока, относящегося только к системам Майкрософт**  
  
## <a name="example"></a>Пример  
 В следующем примере показано, как использовать *argc*, *argv*, и *envp* аргументы `main`:  
  
```cpp 
// argument_definitions.cpp  
// compile with: /EHsc  
#include <iostream>  
#include <string.h>  
  
using namespace std;  
int main( int argc, char *argv[], char *envp[] ) {  
    int iNumberLines = 0;    // Default is no line numbers.  
  
    // If /n is passed to the .exe, display numbered listing  
    // of environment variables.  
  
    if ( (argc == 2) && _stricmp( argv[1], "/n" ) == 0 )  
         iNumberLines = 1;  
  
    // Walk through list of strings until a NULL is encountered.  
    for( int i = 0; envp[i] != NULL; ++i ) {  
        if( iNumberLines )  
            cout << i << ": " << envp[i] << "\n";  
    }  
}  
```  
  
## <a name="see-also"></a>См. также  
 [Функция main: запуск программы](../cpp/main-program-startup.md)