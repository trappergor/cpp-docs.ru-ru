---
title: Определения аргументов
ms.date: 11/04/2016
helpviewer_keywords:
- envp argument
- main function, arguments
- arguments [C++], for main function
- argv argument
- argc argument
ms.assetid: 6148cbf3-ebe8-44f2-b277-de4b723991c7
ms.openlocfilehash: aebd4800ad8d653d532708784ef0a5333211d46b
ms.sourcegitcommit: a6d63c07ab9ec251c48bc003ab2933cf01263f19
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/05/2019
ms.locfileid: "74857662"
---
# <a name="argument-definitions"></a>Определения аргументов

Аргументы в прототипе

```cpp
int main( int argc, char* argv[], char* envp[]);
int wmain( int argc, wchar_t* argv[], wchar_t* envp[]);
```

позволяют удобно выполнять синтаксический разбор аргументов в командной строке и дополнительно осуществлять доступ к переменным среды. Используются следующие определения аргументов.

*argc*<br/>
Целое число, которое содержит число аргументов, следующих за *argv*. Параметр *argc* всегда больше или равен 1.

*argv*<br/>
Массив завершающихся null строк, представляющих введенные пользователем программы аргументы командной строки. По соглашению `argv[0]` — это команда, с помощью которой вызывается программа, `argv[1]` является первым аргументом командной строки и т. д., до `argv[argc]`, которая всегда имеет значение NULL. Сведения о подавлении обработки из командной строки см. в разделе [Настройка обработки командной строки](../cpp/customizing-cpp-command-line-processing.md) .

Первый аргумент командной строки — всегда `argv[1]`, а последний — `argv[argc - 1]`.

> [!NOTE]
> По соглашению `argv[0]` — это команда, с помощью которой вызывается программа.  Однако можно создать процесс с помощью [CreateProcess](/windows/win32/api/libloaderapi/nf-libloaderapi-getmodulefilenamew) и при использовании обоих аргументов (*лпаппликатионнаме* и *лпкоммандлине*), `argv[0]` может не быть именем исполняемого файла; Используйте [GetModuleFileName](/windows/win32/api/libloaderapi/nf-libloaderapi-getmodulefilenamew) , чтобы получить имя исполняемого файла и его полный путь.

**Блок, относящийся только к системам Майкрософт**

*envp*<br/>
Массив *envp* , который является общим расширением во многих системах UNIX, используется в корпорации Майкрософт C++. Это массив строк, представляющих переменные, заданные в среде пользователя. Этот массив завершен записью NULL. Он может быть объявлен как массив указателей на **char** (`char *envp[]`) или как указатель на указатели на **char** (`char **envp`). Если программа использует `wmain` вместо `main`, используйте тип данных **wchar_t** , а не **char**. Блок среды, переданный `main` и `wmain`, является "замороженной" копией текущей среды. При последующем изменении среды с помощью вызова `putenv` или `_wputenv`текущая среда (возвращенная `getenv` или `_wgetenv` и переменная `_environ` или `_wenviron`) изменится, но блок, на который указывает envp, не изменится. Сведения о подавлении обработки среды см. в разделе [Настройка обработки командной строки](../cpp/customizing-cpp-command-line-processing.md) . Этот аргумент совместим с ANSI в C, но не в C++.

**Завершение блока, относящегося только к системам Майкрософт**

## <a name="example"></a>Пример

В следующем примере показано, как использовать аргументы *argc*, *argv*и *envp* для `main`:

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

## <a name="see-also"></a>См. также:

[Функция main: запуск программы](../cpp/main-program-startup.md)