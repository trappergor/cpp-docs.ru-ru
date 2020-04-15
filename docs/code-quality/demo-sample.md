---
title: Пример проекта C++ для анализа кода
description: Как создать образцовое решение для использования в пошаг-прокрутке анализа кода для Microsoft C ' в Visual Studio.
ms.date: 04/14/2020
ms.topic: sample
helpviewer_keywords:
- demo sample [Visual Studio ALM]
- code analysis, samples
ms.assetid: 09e1b9f7-5916-4ed6-a001-5c2d7e710682
ms.openlocfilehash: c2a1b8c80b7e7aebd1f1530c66ade5859b392028
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81372059"
---
# <a name="sample-c-project-for-code-analysis"></a>Пример проекта C++ для анализа кода

Следующие процедуры показывают, как создать образец для [Walkthrough: Анализ кода C/C' для дефектов.](../code-quality/walkthrough-analyzing-c-cpp-code-for-defects.md) Эти процедуры создают следующее:

- Решение Visual Studio под названием *CppDemo*.

- Проект статической библиотеки под названием *CodeDefects*.

- Проект статической библиотеки под названием *Аннотации*.

Кроме того, эти процедуры предоставляют код для заголовка и *CPP*-файлов для статических библиотек.

## <a name="create-the-cppdemo-solution-and-the-codedefects-project"></a>Создание решения CppDemo и проекта CodeDefects

::: moniker range=">=vs-2019"

1. Откройте visual Studio и выберите **Создать новый проект**

1. В **диалоге «Создать новый проект»** измените языковой фильтр на **C'»**.

1. Выберите **Windows Desktop Wizard** и выберите **кнопку «Следующая».**

1. На новой странице **проекта,** в текстовом поле **названия проекта,** введите *CodeDefects.*

1. В текстовом окне **имени решения** введите *CppDemo*.

1. Выберите **Создать**.

1. В диалоге **проекта Windows Desktop** измените тип **приложения** на Static **Library (.lib).**

1. В поле **Дополнительные параметры**выберите **Пустой проект**.

1. Выберите **OK** для создания решения и проекта.

::: moniker-end

::: moniker range="vs-2017"

1. Запустите Visual Studio. В меню-баре выберите **File** > **New** > **Project.**

1. В диалоге **нового проекта** выберите **визуальный** > **рабочий стол Windows**Desktop.

1. Выберите **windows Desktop Wizard**.

1. В текстовом окне **name** введите *CodeDefects*.

1. В текстовом окне **имени решения** введите *CppDemo*.

1. Выберите **OK**.

1. В диалоге **проекта Windows Desktop** измените тип **приложения** на Static **Library (.lib).**

1. В поле **Дополнительные параметры**выберите **Пустой проект**.

1. Выберите **OK** для создания решения и проекта.

::: moniker-end

::: moniker range="vs-2015"

1. Запустите Visual Studio. В меню-баре выберите **File** > **New** > **Project.**

1. В диалоге **нового проекта** выберите **шаблоны** > **Visual C'** > **Win32**.

1. Выберите **консольное приложение Win32**.

1. В текстовом окне **name** введите *CodeDefects*.

1. В текстовом окне **имени решения** введите *CppDemo*.

1. Выберите **OK**.

1. В диалоге **Win32 Wizard,** выберите **следующую** кнопку.

1. Измените **тип приложения** в **статической библиотеке.**

1. Под **дополнительными опциями**невыбрать **предварительно собранный заголовок.**

1. Выберите **Finish,** чтобы создать решение и проект.

::: moniker-end

## <a name="add-the-header-and-source-file-to-the-codedefects-project"></a>Добавление заголовка и исходного файла в проект CodeDefects

1. В Solution Explorer расширьте **CodeDefects.**

1. Нажмите правой кнопкой мыши, чтобы открыть контекстное меню для **файлов заголовков.** Выберите **Добавить** > **новый пункт**.

1. В диалоговом окне **Добавить новый элемент** выберите**визуальный код** **C,** > а затем выберите **файл заголовка (.h).**

1. В поле **Name** edit введите *Bug.h,* а затем выберите кнопку **Добавить.**

1. В окне отображаемого для *Bug.h*, выберите и удалите содержимое.

1. Скопируйте приведенный ниже код и вставьте его в файл *Bug.h* в редакторе.

    ```cpp
    #pragma once

    #include <windows.h>

    // Function prototypes
    bool CheckDomain(wchar_t const *);
    HRESULT ReadUserAccount();

    // These constants define the common sizes of the
    // user account information throughout the program
    const int USER_ACCOUNT_LEN = 256;
    const int ACCOUNT_DOMAIN_LEN = 128;
    ```

1. В Solution Explorer нажмите правой кнопкой мыши, чтобы открыть контекстное меню для **исходных файлов.** Выберите **Добавить** > **новый пункт**.

1. В диалоговом окне **Добавление нового элемента** выберите **Файл C++ (.cpp)**.

1. В поле **Name** edit введите *Bug.cpp,* а затем выберите кнопку **Добавить.**

1. Скопируйте приведенный ниже код и вставьте его в файл *Bug.cpp* в редакторе.

    ```cpp
    #include "Bug.h"

    // the user account
    wchar_t g_userAccount[USER_ACCOUNT_LEN] = { L"domain\\user" };
    int len = 0;

    bool CheckDomain(wchar_t const* domain)
    {
        return (wcsnlen_s(domain, USER_ACCOUNT_LEN) > 0);
    }

    HRESULT ReadUserAccount()
    {
        return S_OK;
    }

    bool ProcessDomain()
    {
        wchar_t* domain = new wchar_t[ACCOUNT_DOMAIN_LEN];
        // ReadUserAccount gets a 'domain\user' input from
        //the user into the global 'g_userAccount'
        if (ReadUserAccount())
        {
            // Copies part of the string prior to the '\'
            // character onto the 'domain' buffer
            for (len = 0; (len < ACCOUNT_DOMAIN_LEN) && (g_userAccount[len] != L'\0'); len++)
            {
                if (g_userAccount[len] == L'\\')
                {
                    // Stops copying on the domain and user separator ('\')
                    break;
                }
                domain[len] = g_userAccount[len];
            }
            if ((len = ACCOUNT_DOMAIN_LEN) || (g_userAccount[len] != L'\\'))
            {
                // '\' was not found. Invalid domain\user string.
                delete[] domain;
                return false;
            }
            else
            {
                domain[len] = L'\0';
            }
            // Process domain string
            bool result = CheckDomain(domain);

            delete[] domain;
            return result;
        }
        return false;
    }

    int path_dependent(int n)
    {
        int i;
        int j;
        if (n == 0)
            i = 1;
        else
            j = 1;
        return i + j;
    }
    ```

1. В баре меню выберите **Файл** > **Сохранить все**.

## <a name="add-the-annotations-project-and-configure-it-as-a-static-library"></a>Добавление проекта Annotations и его настройка в качестве статической библиотеки

::: moniker range=">=vs-2019"

1. В Solution Explorer, правой кнопкой мыши **CppDemo,** чтобы открыть контекстное меню. Выберите **Добавить** > **новый проект**.

1. В **добавлении нового** окна диалога проекта выберите **Windows Desktop Wizard,** а затем выберите **кнопку «Следующая».**

1. На новой странице **проекта,** в текстовом поле **названия проекта,** введите *аннотации,* а затем выберите **Создать**.

1. В диалоге **проекта Windows Desktop** измените тип **приложения** на Static **Library (.lib).**

1. В поле **Дополнительные параметры**выберите **Пустой проект**.

1. Выберите **OK** для создания проекта.

::: moniker-end

::: moniker range="vs-2017"

1. В Solution Explorer, правой кнопкой мыши **CppDemo,** чтобы открыть контекстное меню. Выберите **Добавить** > **новый проект**.

1. В диалоге **Добавить новый проект** выберите **визуальный** > **рабочий стол Windows**Desktop.

1. Выберите **windows Desktop Wizard**.

1. В текстовом окне **name** введите *аннотации,* а затем выберите **OK.**

1. В диалоге **проекта Windows Desktop** измените тип **приложения** на Static **Library (.lib).**

1. В поле **Дополнительные параметры**выберите **Пустой проект**.

1. Выберите **OK** для создания проекта.

::: moniker-end

::: moniker range="vs-2015"

1. В Solution Explorer, правой кнопкой мыши **CppDemo,** чтобы открыть контекстное меню. Выберите **Добавить** > **новый проект**.

1. В диалоге **Добавить новый проект** выберите **Visual C'** > **Win32**.

1. Выберите **консольное приложение Win32**.

1. В текстовом окне **имени** введите *аннотации.*

1. Выберите **OK**.

1. В диалоге **Win32 Wizard,** выберите **следующую** кнопку.

1. Измените **тип приложения** в **статической библиотеке.**

1. Под **дополнительными опциями**невыбрать **предварительно собранный заголовок.**

1. Выберите **finish** для создания проекта.

::: moniker-end

## <a name="add-the-header-file-and-source-file-to-the-annotations-project"></a>Добавление файла заголовка и исходного файла в проект Annotations

1. В Solution Explorer расширьте **аннотации.**

1. Нажмите правой кнопкой мыши, чтобы открыть контекстное меню файлов **заголовка** под **аннотациями.** Выберите **Добавить** > **новый пункт**.

1. В диалоговом окне **Добавить новый элемент** выберите**визуальный код** **C,** > а затем выберите **файл заголовка (.h).**

1. В поле **Name** edit введите *annotations.h,* а затем выберите кнопку **Добавить.**

1. В окне отображения для *annotations.h*выберите и удалите содержимое.

1. Скопируйте приведенный ниже код и вставьте его в файл *annotations.h* в редакторе.

    ```cpp
    #pragma once
    #include <sal.h>

    struct LinkedList
    {
        struct LinkedList* next;
        int data;
    };

    typedef struct LinkedList LinkedList;

    _Ret_maybenull_ LinkedList* AllocateNode();
    ```

1. В Solution Explorer нажмите правой кнопкой мыши, чтобы открыть контекстное меню для **исходных файлов** под **аннотациями.** Выберите **Добавить** > **новый пункт**.

1. В диалоговом окне **Добавление нового элемента** выберите **Файл C++ (.cpp)**.

1. В поле **Name** edit введите *annotations.cpp,* а затем выберите кнопку **Добавить.**

1. Скопируйте приведенный ниже код и вставьте его в файл *annotations.cpp* в редакторе.

    ```cpp
    #include "annotations.h"
    #include <malloc.h>

    _Ret_maybenull_ LinkedList* AllocateNode()
    {
        LinkedList* result = static_cast<LinkedList*>(malloc(sizeof(LinkedList)));
        return result;
    }

    LinkedList* AddTail(LinkedList* node, int value)
    {
        // finds the last node
        while (node->next != nullptr)
        {
            node = node->next;
        }

        // appends the new node
        LinkedList* newNode = AllocateNode();
        newNode->data = value;
        newNode->next = 0;
        node->next = newNode;

        return newNode;
    }
    ```

1. В баре меню выберите **Файл** > **Сохранить все**.

Теперь решение завершено и должно создаться без ошибок.

::: moniker range="vs-2017"

> [!NOTE]
> В Visual Studio 2017 вы можете увидеть `E1097 unknown attribute "no_init_all"` ложное предупреждение в движке IntelliSense. Это предупреждение можно проигнорировать.

::: moniker-end
