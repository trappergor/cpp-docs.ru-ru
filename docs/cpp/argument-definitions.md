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
ms.openlocfilehash: 14e5ea3a051d81828c5f88ac16df60b6ebb5b559
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/15/2019
ms.locfileid: "69498819"
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
Массив завершающихся null строк, представляющих введенные пользователем программы аргументы командной строки. По соглашению `argv[0]` — это команда, с помощью которой вызывается программа, `argv[1]` является первым аргументом командной строки и т. д., до `argv[argc]`которой всегда имеет значение null. Сведения о подавлении обработки из командной строки см. в разделе [Настройка обработки командной строки](../cpp/customizing-cpp-command-line-processing.md) .

Первый аргумент командной строки — всегда `argv[1]`, а последний — `argv[argc - 1]`.

> [!NOTE]
> По соглашению `argv[0]` — это команда, с помощью которой вызывается программа.  Однако можно создать процесс с помощью [CreateProcess](/windows/win32/api/libloaderapi/nf-libloaderapi-getmodulefilenamew) и, если вы используете как первый, так и второй аргумент (*лпаппликатионнаме* и *лпкоммандлине*), `argv[0]` не может быть именем исполняемого файла; используйте [GetModuleFileName ](/windows/win32/api/libloaderapi/nf-libloaderapi-getmodulefilenamew), чтобы получить имя исполняемого файла и полный путь к нему.

## <a name="microsoft-specific"></a>Блок, относящийся только к системам Microsoft

*envp*<br/>
Массив *envp* , который является общим расширением во многих системах UNIX, используется в корпорации Майкрософт C++. Это массив строк, представляющих переменные, заданные в среде пользователя. Этот массив завершается записью NULL. Он может быть объявлен как массив указателей на **char** `char *envp[]`() или как указатель на указатели на **char** (`char **envp`). Если `wmain` программа использует `main`вместо, используйте тип данных **wchar_t** вместо **char**. Блок среды, переданный `main` в `wmain` и, является замороженной копией текущей среды. При последующем изменении `putenv` среды с помощью вызова или `_wputenv`, текущая `getenv` среда (как и `_wenviron` переменная или, `_environ` возвращаемая `_wgetenv` переменной или) изменится, но блок, на который указывает envp не изменится. Сведения о подавлении обработки среды см. в разделе [Настройка обработки командной строки](../cpp/customizing-cpp-command-line-processing.md) . Этот аргумент совместим с ANSI в C, но не в C++.

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

## <a name="see-also"></a>См. также

[main: запуск программы](../cpp/main-program-startup.md)