---
title: Библиотеки DLL и поведение библиотеки времени выполнения Visual C++
ms.date: 08/19/2019
f1_keywords:
- _DllMainCRTStartup
- CRT_INIT
helpviewer_keywords:
- DLLs [C++], entry point function
- process detach [C++]
- process attach [C++]
- DLLs [C++], run-time library behavior
- DllMain function
- _CRT_INIT macro
- _DllMainCRTStartup method
- run-time [C++], DLL startup sequence
- DLLs [C++], startup sequence
ms.assetid: e06f24ab-6ca5-44ef-9857-aed0c6f049f2
ms.openlocfilehash: 2f2ffb13e6a80b144298bbf8cd76b5666a10b4dd
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81335663"
---
# <a name="dlls-and-visual-c-run-time-library-behavior"></a>Библиотеки DLL и поведение библиотеки времени выполнения Visual C++

При создании библиотеки динамической ссылки (DLL) с помощью Visual Studio по умолчанию ссылка включает в себя библиотеку времени выполнения Visual C (VCRuntime). VCRuntime содержит код, необходимый для инициализации и прекращения выполнения C/C. При подключении к DLL код VCRuntime обеспечивает внутреннюю `_DllMainCRTStartup` функцию входа DLL, называемую, которая обрабатывает сообщения ОС Windows в DLL для присоединения или отступления от процесса или потока. Функция `_DllMainCRTStartup` выполняет важные задачи, такие как настройка буферной безопасности стека, инициализация и завершение библиотеки c run-time (CRT), а также вызовы конструкторам и деструкторам для статических и глобальных объектов. `_DllMainCRTStartup`также вызывает функции крючка для других библиотек, таких как WinRT, MFC и ATL для выполнения их собственной инициализации и прекращения. Без этой инициализации CRT и другие библиотеки, а также ваши статические переменные будут оставлены в непреницуемом состоянии. Те же процедуры внутренней инициализации и прекращения VCRuntime называются независимо от того, использует ли ваш DLL статически связанную CRT или динамически связанную CRT DLL.

## <a name="default-dll-entry-point-_dllmaincrtstartup"></a>Точка входа DLL по умолчанию _DllMainCRTStartup

В Windows все DLL могут содержать дополнительную функцию начальной точки, обычно называемую `DllMain`, которая требует как инициализации, так и прекращения. Это дает вам возможность выделить или высвободить дополнительные ресурсы по мере необходимости. Windows вызывает функцию точки входа в четырех ситуациях: присоединение процесса, отсоединение процесса, присоединение потока и отсоединение потоков. При загрузке DLL в адресное пространство процесса, когда приложение, используюеее его, или когда приложение запрашивает DLL во время выполнения, операционная система создает отдельную копию данных DLL. Это называется *присоединением процесса.* *Присоединение потока* происходит, когда процесс загрузки DLL создает новый поток. *Отсоединить поток* происходит, когда поток завершается, и *процесс отсоединяется,* когда DLL больше не требуется и освобождается приложением. Операционная система делает отдельный вызов в точку входа DLL для каждого из этих событий, передавая *аргумент причины* для каждого типа события. Например, ОС `DLL_PROCESS_ATTACH` посылает в качестве *аргумента причины* для прикрепления процесса сигнала.

Библиотека VCRuntime предоставляет функцию начальной точки, называемую `_DllMainCRTStartup` для обработки операций инициализации и прекращения по умолчанию. При подключении `_DllMainCRTStartup` процесса функция настраивает проверки безопасности буфера, инициализирует CRT и другие библиотеки, инициализирует информацию о типе времени выполнения, инициализирует и вызывает конструкторов для статических `DllMain`и нелокальных данных, инициализирует хранение потоков-локальных, приращает внутренний статический счетчик для каждого прикрепления, а затем вызывает пользователь- или библиотеку-поставляется. При отъезде процесса функция проходит через эти шаги в обратном направлении. Он `DllMain`вызывает, decrements внутренний счетчик, вызывает destructors, `atexit` вызывает функции прекращения CRT и зарегистрированные функции, и уведомляет любые другие библиотеки прекращения. Когда счетчик вложений сходит `FALSE` на ноль, функция возвращается, чтобы указать Windows, что DLL может быть выгружен. Функция `_DllMainCRTStartup` также вызывается во время прикрепления потока и отсоединить поток. В этих случаях код VCRuntime не делает никакой дополнительной инициализации или прекращения самостоятельно, а просто призывает `DllMain` передать сообщение вместе. Если `DllMain` `FALSE` возвращается из процесса прикрепить, сигнализации `_DllMainCRTStartup` сбоя, `DllMain` звонки снова и проходит `DLL_PROCESS_DETACH` в качестве *аргумента причины,* а затем проходит через остальную часть процесса прекращения.

При создании DLL в Visual Studio `_DllMainCRTStartup` точка входа по умолчанию, поставляемая VCRuntime, автоматически связана. Вам не нужно указывать функцию точки входа для вашего DLL, используя опцию [linker /ENTRY (символ точки входа).](reference/entry-entry-point-symbol.md)

> [!NOTE]
> Хотя можно указать другую функцию точки входа для DLL с помощью опции /ENTRY: linker, мы не рекомендуем `_DllMainCRTStartup` его, потому что ваша функция точки входа должна была бы дублировать все, что делает, в том же порядке. VCRuntime предоставляет функции, которые позволяют дублировать его поведение. Например, можно вызвать [__security_init_cookie](../c-runtime-library/reference/security-init-cookie.md) сразу при подключении процесса для поддержки опции проверки буфера [/GS (Buffer security check).](reference/gs-buffer-security-check.md) Вы можете `_CRT_INIT` вызвать функцию, передавая те же параметры, что и функция точки входа, для выполнения остальных функций инициализации или прекращения DLL.

<a name="initializing-a-dll"></a>

## <a name="initialize-a-dll"></a>Инициализация DLL

Ваш DLL может иметь код инициализации, который должен выполняться при загрузке DLL. Для того, чтобы вы могли выполнять свои собственные `_DllMainCRTStartup` функции `DllMain` инициализации и прекращения DLL, вызывает функцию, которую вы можете предоставить. У `DllMain` вас должна быть подпись, необходимая для точки входа DLL. Функция `_DllMainCRTStartup` точки входа `DllMain` по умолчанию вызывает с использованием тех же параметров, пройдено Windows. По умолчанию, если вы `DllMain` не предоставляете функцию, Visual Studio `_DllMainCRTStartup` предоставляет один для вас и связывает его так, что всегда есть что-то позвонить. Это означает, что если вам не нужно инициализировать DLL, нет ничего особенного вы должны сделать при создании DLL.

Это подпись, используемая для: `DllMain`

```cpp
#include <windows.h>

extern "C" BOOL WINAPI DllMain (
    HINSTANCE const instance,  // handle to DLL module
    DWORD     const reason,    // reason for calling function
    LPVOID    const reserved); // reserved
```

Некоторые библиотеки `DllMain` обернут функцию для вас. Например, в обычном MFC DLL реализуйте функции `CWinApp` объекта `InitInstance` и `ExitInstance` члена для выполнения инициализации и прекращения, требуемых вашим DLL. Для получения более подробной информации см. [Initialize regular MFC DLLs](#initializing-regular-dlls)

> [!WARNING]
> Существуют значительные ограничения на то, что вы можете безопасно сделать в точке входа DLL. Ознакомьтесь с [общими рекомендациями](/windows/win32/Dlls/dynamic-link-library-best-practices) для конкретных AIS Windows, которые небезопасны для `DllMain`вызова. Если вам нужно что-нибудь, но простейшая инициализация, то сделайте это в функции инициализации для DLL. Вы можете потребовать, чтобы приложения `DllMain` повызову функции инициализации после запуска и до того, как они вызовут какие-либо другие функции в DLL.

<a name="initializing-non-mfc-dlls"></a>

### <a name="initialize-ordinary-non-mfc-dlls"></a>Инициализация обычных (не МФК) ДлЛ

Для выполнения собственной инициализации в обычных (не-MFC) DLL, которые используют `_DllMainCRTStartup` VCRuntime-поставляется `DllMain`точка входа, ваш исходный код DLL должен содержать функцию, называемую . Следующий код представляет основной скелет, `DllMain` показывающий, как может выглядеть определение:

```cpp
#include <windows.h>

extern "C" BOOL WINAPI DllMain (
    HINSTANCE const instance,  // handle to DLL module
    DWORD     const reason,    // reason for calling function
    LPVOID    const reserved)  // reserved
{
    // Perform actions based on the reason for calling.
    switch (reason)
    {
    case DLL_PROCESS_ATTACH:
        // Initialize once for each new process.
        // Return FALSE to fail DLL load.
        break;

    case DLL_THREAD_ATTACH:
        // Do thread-specific initialization.
        break;

    case DLL_THREAD_DETACH:
        // Do thread-specific cleanup.
        break;

    case DLL_PROCESS_DETACH:
        // Perform any necessary cleanup.
        break;
    }
    return TRUE;  // Successful DLL_PROCESS_ATTACH.
}
```

> [!NOTE]
> В старой документации Windows SDK говорится, что фактическое название функции точки входа DLL должно быть указано в командной строке linker с опцией /ENTRY. С Visual Studio вам не нужно использовать опцию /ENTRY, если имя `DllMain`вашей функции начальной точки. В самом деле, если вы используете / ENTRY вариант `DllMain`и имя вашей функции начальной точки что-то другое, `_DllMainCRTStartup` CRT не получить инициализированы должным образом, если ваша функция начальной точки делает тот же инициализации звонки, что делает.

<a name="initializing-regular-dlls"></a>

### <a name="initialize-regular-mfc-dlls"></a>Инициализация регулярных DLL MFC

Поскольку у регулярных `CWinApp` DL-адресов MFC есть объект, они должны выполнять свои задачи `InitInstance` инициализации и прекращения в том же месте, что и приложение MFC: в функциях и `ExitInstance` функциях члена класса `CWinApp`DLL. Потому что `DllMain` MFC предоставляет `_DllMainCRTStartup` функцию, которая называется для `DLL_PROCESS_ATTACH` и `DLL_PROCESS_DETACH`, вы не должны писать свою собственную `DllMain` функцию. Функция MFC, `DllMain` предоставленная MFC, вызывает сявт, `InitInstance` когда ваш DLL загружается и звонит `ExitInstance` до выгрузки DLL.

Регулярный MFC DLL может отслеживать несколько потоков, вызывая [TlsAlloc](/windows/win32/api/processthreadsapi/nf-processthreadsapi-tlsalloc) и [TlsGetValue](/windows/win32/api/processthreadsapi/nf-processthreadsapi-tlsgetvalue) в своей `InitInstance` функции. Эти функции позволяют DLL отслеживать данные, относясь к потокам.

В вашем регулярном MFC DLL, что динамически ссылки на MFC, если вы используете любой MFC OLE, MFC базы данных (или DAO), или MFC Розетки поддержки, соответственно, отладить MFC расширение DLLs MFCO*версия*D.dll, MFCD*версия*Dll, и MFCN*версия*D.dll (где *версия* номер версии) связаны автоматически. Вы должны позвонить в одну из следующих предопределенных функций инициализации для каждого `CWinApp::InitInstance`из этих DLLs, которые вы используете в вашей обычной MFC DLL' .

|Тип поддержки МФЦ|Функция инициализации для вызова|
|-------------------------|-------------------------------------|
|MFC OLE *(MFCO версия*D.dll)|`AfxOleInitModule`|
|База данных МФЦ *(MFCD версия*D.dll)|`AfxDbInitModule`|
|MFC Sockets *(MFCN версия*D.dll)|`AfxNetInitModule`|

<a name="initializing-extension-dlls"></a>

### <a name="initialize-mfc-extension-dlls"></a>Инициализация DLL расширения MFC

Поскольку DLL расширения MFC `CWinApp`не имеют объекта, полученного из-производного (как это делают `DllMain` обычные DLL MFC), следует добавить код инициализации и прекращения к функции, которую генерирует MFC DLL Wizard.

Мастер предоставляет следующий код для DLL расширения MFC. В `PROJNAME` коде, является заполнителем для названия вашего проекта.

```cpp
#include "pch.h" // For Visual Studio 2017 and earlier, use "stdafx.h"
#include <afxdllx.h>

#ifdef _DEBUG
#define new DEBUG_NEW
#undef THIS_FILE
static char THIS_FILE[] = __FILE__;
#endif
static AFX_EXTENSION_MODULE PROJNAMEDLL = { NULL, NULL };

extern "C" int APIENTRY
DllMain(HINSTANCE hInstance, DWORD dwReason, LPVOID lpReserved)
{
   if (dwReason == DLL_PROCESS_ATTACH)
   {
      TRACE0("PROJNAME.DLL Initializing!\n");

      // MFC extension DLL one-time initialization
      AfxInitExtensionModule(PROJNAMEDLL,
                                 hInstance);

      // Insert this DLL into the resource chain
      new CDynLinkLibrary(Dll3DLL);
   }
   else if (dwReason == DLL_PROCESS_DETACH)
   {
      TRACE0("PROJNAME.DLL Terminating!\n");
   }
   return 1;   // ok
}
```

Создание нового `CDynLinkLibrary` объекта во время инициализации `CRuntimeClass` позволяет DLL расширения MFC экспортировать объекты или ресурсы в клиентское приложение.

Если вы собираетесь использовать расширение MFC DLL от одного или нескольких регулярных DLL MFC, вы должны экспортировать функцию инициализации, которая создает `CDynLinkLibrary` объект. Эта функция должна быть вызвана от каждого из регулярных DLL MFC, которые используют расширение MFC DLL. Подходящее место для вызова этой функции инициализации находится в функции `InitInstance` члена регулярного MFC `CWinApp`DLL-производные объекта, прежде чем использовать любой из расширения MFC DLL экспортируется классов или функций.

В `DllMain` том, что MFC DLL Wizard `AfxInitExtensionModule` генерирует, вызов для захвата классов`CRuntimeClass` времени выполнения модуля (структуры), а также его объекты заводов (объектов)`COleObjectFactory` для использования при создании `CDynLinkLibrary` объекта. Вы должны проверить возвратное `AfxInitExtensionModule`значение; если нулевое значение `AfxInitExtensionModule`возвращается из, `DllMain` возвратнул ноль из вашей функции.

Если ваше расширение MFC DLL будет явно связано с исполняемым `AfxLoadLibrary` (имеется в виду исполняемые `AfxTermExtensionModule` вызовы для ссылки на DLL), вы должны добавить вызов на `DLL_PROCESS_DETACH`. Эта функция позволяет MFC очистить расширение MFC DLL, когда каждый процесс отделяется от расширения MFC DLL (что происходит, когда процесс `AfxFreeLibrary` выходит или когда DLL выгружается в результате вызова). Если ваше расширение MFC DLL будет неявно привязано `AfxTermExtensionModule` к приложению, звонок не требуется.

Приложения, которые явно ссылаются на DLL расширения MFC должны звонить `AfxTermExtensionModule` при освобождении DLL. Они также `AfxLoadLibrary` должны `AfxFreeLibrary` использовать и (вместо `LoadLibrary` функций Win32 и) `FreeLibrary`если приложение использует несколько потоков. Использование `AfxLoadLibrary` `AfxFreeLibrary` и обеспечение того, чтобы код запуска и выключения, выполняемый при загрузке и выгрузке расширения MFC, не поручивал глобальное состояние MFC.

Поскольку MFCx0.dll полностью инициализирован к моменту `DllMain` вызова, можно `DllMain` выделить функции памяти и вызова MFC в пределах (в отличие от 16-битной версии MFC).

Расширение DLLs может заботиться о многопоточности путем обработки `DLL_THREAD_ATTACH` и `DLL_THREAD_DETACH` случаев в функции. `DllMain` Эти случаи `DllMain` передаются при присоединении и отсоединении потоков от DLL. Вызов [TlsAlloc](/windows/win32/api/processthreadsapi/nf-processthreadsapi-tlsalloc) при подключении DLL позволяет DLL поддерживать локальные индексы хранения потоков (TLS) для каждого потока, прикрепленного к DLL.

Обратите внимание, что файл заголовка Afxdllx.h содержит специальные определения для структур, используемых `CDynLinkLibrary`в DLL расширения MFC, таких как определение и `AFX_EXTENSION_MODULE` . Вы должны включить этот файл заголовка в DLL расширения MFC.

> [!NOTE]
> Важно, чтобы вы не определяли `_AFX_NO_XXX` и не не определяли ни один из макросов в *pch.h* *(stdafx.h* в Visual Studio 2017 и более раньше). Эти макросы существуют только для проверки того, поддерживает ли эта функция конкретная целевая платформа или нет. Вы можете написать программу, чтобы проверить `#ifndef _AFX_NO_OLE_SUPPORT`эти макросы (например, ), но ваша программа никогда не должна определять или не определять эти макросы.

Функция инициализации образцов, которая обрабатывает многопоточность, включена в [функцию «Использование локального хранения потоков» в библиотеке Dynamic-Link](/windows/win32/Dlls/using-thread-local-storage-in-a-dynamic-link-library) в SDK СДК с Windows. Обратите внимание, что образец содержит `LibMain`функцию начальной `DllMain` точки, называемую, но эту функцию следует назвать так, чтобы она работала с библиотеками mFC и C.

## <a name="see-also"></a>См. также раздел

[Создание библиотек DLL C/C++ в Visual Studio](dlls-in-visual-cpp.md)<br/>
[DllMain точка входа](/windows/win32/Dlls/dllmain)<br/>
[Рекомендации библиотеки динамической связи](/windows/win32/Dlls/dynamic-link-library-best-practices)
