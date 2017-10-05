---
title: "Определения аргументов | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
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
caps.latest.revision: 13
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 6ffef5f51e57cf36d5984bfc43d023abc8bc5c62
ms.openlocfilehash: d50e32a54cdb10af4adbfb3cfda64b8f1b21b2eb
ms.contentlocale: ru-ru
ms.lasthandoff: 09/25/2017

---
# <a name="argument-definitions"></a>Определения аргументов
Аргументы в прототипе  
  
```  
  
int main( int  
argc[ ,char*argv[] [,char*envp[] ] ] );intwmain(intargc[ ,wchar_t*argv[] [,wchar_t*envp[] ] ] );  
```  
  
 позволяют удобно выполнять синтаксический разбор аргументов в командной строке и дополнительно осуществлять доступ к переменным среды. Используются следующие определения аргументов.  
  
 `argc`  
 Целое число, которое содержит количество аргументов, следующих в `argv`. Параметр `argc` всегда больше или равен 1.  
  
 `argv`  
 Массив завершающихся null строк, представляющих введенные пользователем программы аргументы командной строки. По соглашению `argv` **[0]** — команда, с помощью которого вызывается программа, `argv` **[1]** является первым аргументом командной строки и т. д., пока не `argv` ** [**`argc`**]**, который всегда имеет **NULL**. В разделе [Настройка обработки командной строки](../cpp/customizing-cpp-command-line-processing.md) сведения о подавлении обработки в командной строке.  
  
 Первый аргумент командной строки — всегда `argv` **[1]** , а последний — `argv` **[** `argc` - 1**]**.  
  
> [!NOTE]
>  По соглашению параметр `argv`**[0]** содержит команду, которая использовалась для вызова программы.  Тем не менее, можно создать процесс с помощью [CreateProcess](http://msdn.microsoft.com/library/windows/desktop/ms683197) и при использовании первый и второй аргументы (`lpApplicationName` и `lpCommandLine`), `argv` **[0]** не может быть Имя исполняемого файла; Используйте [GetModuleFileName](http://msdn.microsoft.com/library/windows/desktop/ms683197) для получения его полный путь и имя исполняемого файла.  
  
## <a name="microsoft-specific"></a>Блок, относящийся только к системам Microsoft  
 `envp`  
 Массив `envp`, представляющий собой общее расширение во многих системах UNIX, используется в Microsoft C++. Это массив строк, представляющих переменные, заданные в среде пользователя. Этот массив завершен **NULL** входа. Его можно объявить как массив указателей на **char (char** \*envp []**)** или как указатель на указатели на **char (char** \* \* envp**)**. Если программа использует **wmain** вместо **основной**, используйте `wchar_t` вместо типа данных `char`. Блок среды, передаваемый **основной** и **wmain** является «зафиксированной» копией текущей среды. При изменении среды через вызов **putenv** или `_wputenv`, текущая среда (возвращенная `getenv` / `_wgetenv` и `_environ` /  `_wenviron` переменную) блок, на который указывает envp но изменение будет не изменится. В разделе [Настройка обработки командной строки](../cpp/customizing-cpp-command-line-processing.md) сведения о подавлении обработки в среде. Этот аргумент совместим с ANSI в C, но не в C++.  
  
**Завершение блока, относящегося только к системам Майкрософт**  
  
## <a name="example"></a>Пример  
 В следующем примере показано, как использовать `argc`, `argv`, и `envp` аргументы **основной**:  
  
```  
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
