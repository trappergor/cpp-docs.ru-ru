---
title: Использование библиотек DLL расширений MFC для баз данных, OLE и сокетов в обычных библиотеках DLL MFC
ms.date: 11/04/2016
helpviewer_keywords:
- DLLs [C++], initializing
- DLLs [C++], extension
- DLLs [C++], regular
ms.assetid: 9f1d14a7-9e2a-4760-b3b6-db014fcdb7ff
ms.openlocfilehash: 3d516f7923144f0e24bda676147ed529546def25
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87213766"
---
# <a name="using-database-ole-and-sockets-mfc-extension-dlls-in-regular-mfc-dlls"></a>Использование библиотек DLL расширений MFC для баз данных, OLE и сокетов в обычных библиотеках DLL MFC

При использовании библиотеки DLL расширения MFC из обычной библиотеки DLL MFC, если библиотека DLL расширения MFC не привязана к цепочке объектов **CDynLinkLibrary** обычной библиотеки DLL MFC, вы можете столкнуться с проблемами. Поскольку отладочные версии библиотек DLL с поддержкой баз данных MFC, OLE и сокетов реализуются как библиотеки DLL расширения MFC, при использовании этих функций MFC могут возникнуть аналогичные проблемы, даже если вы не используете явно какие-либо собственные библиотеки расширения MFC. Некоторые симптомы:

- При попытке десериализации объекта типа класса, определенного в библиотеке DLL расширения MFC, в окне отладки TRACE выдается сообщение: "Предупреждение. Не удается загрузить CYourClass из архива. Класс не определен". В результате не удается выполнить сериализацию объекта.

- Может быть вызвано исключение, указывающее на недопустимый класс.

- Не удается загрузить ресурсы, хранящиеся в библиотеке DLL расширения MFC, так как `AfxFindResourceHandle` возвращает **NULL** или неправильный дескриптор ресурса.

- `DllGetClassObject`, `DllCanUnloadNow` и функции-члены `UpdateRegistry`, `Revoke`, `RevokeAll` и `RegisterAll` в `COleObjectFactory` не могут найти фабрику класса, определенную в библиотеке DLL расширения MFC.

- `AfxDoForAllClasses` не работает ни для каких классов в библиотеке DLL расширения MFC.

- Не удается загрузить стандартные базы данных MFC, сокеты или ресурсы OLE. Например, **AfxLoadString**(**AFX_IDP_SQL_CONNECT_FAIL**) возвращает пустую строку, даже если обычная библиотека DLL MFC правильно использует классы базы данных MFC.

Решение этих проблем заключается в создании и экспорте функции инициализации в библиотеке DLL расширения MFC, которая создает объект **CDynLinkLibrary**. Вызывайте эту функцию инициализации ровно один раз из каждой обычной библиотеки DLL MFC, использующей библиотеку DLL расширения MFC.

## <a name="mfc-ole-mfc-database-or-dao-or-mfc-sockets-support"></a>Поддержка MFC OLE, базы данных MFC (или DAO) или сокетов MFC

Если вы используете поддержку MFC OLE, базы данных MFC (или DAO) или сокетов MFC соответственно, отладочные библиотеки DLL расширения MFC MFCOxxD.dll, MFCDxxD.dll и MFCNxxD.dll (где xx — номер версии) связываются автоматически. Необходимо вызвать предопределенную функцию инициализации для каждой из этих используемых библиотек DLL.

Для поддержки базы данных добавьте вызов `AfxDbInitModule` в функцию `CWinApp::InitInstance` для обычной библиотеки DLL MFC. Убедитесь, что этот вызов происходит перед вызовом базового класса или любым добавленным кодом, который обращается к MFCDxxD.dll. Эта функция не принимает параметры и возвращает пустое значение.

Для поддержки OLE добавьте вызов `AfxOleInitModule` в функцию `CWinApp::InitInstance` для обычной библиотеки DLL MFC. Обратите внимание, что функция **COleControlModule InitInstance** уже вызывает `AfxOleInitModule`, поэтому, если вы создаете элемент управления OLE и используете `COleControlModule`, не следует добавлять этот вызов в `AfxOleInitModule`.

Для поддержки сокетов добавьте вызов `AfxNetInitModule` в функцию `CWinApp::InitInstance` для обычной библиотеки DLL MFC.

Обратите внимание, что сборки выпусков библиотек DLL и приложений MFC не используют отдельные библиотеки DLL для поддержки баз данных, сокетов и OLE. Тем не менее в режиме выпуска можно спокойно вызывать эти функции инициализации.

## <a name="cdynlinklibrary-objects"></a>Объекты CDynLinkLibrary

При каждой операции, упомянутой в начале этого раздела, MFC необходимо найти нужное значение или объект. Например, во время десериализации MFC должен выполнять поиск по всем доступным в настоящее время классам среды выполнения для сопоставления объектов в архиве с соответствующим классом времени выполнения.

В рамках этого поиска MFC сканирует все библиотеки DLL расширения MFC, проходя по цепочке объектов **CDynLinkLibrary**. Объекты **CDynLinkLibrary** автоматически присоединяются к цепочке во время создания и создаются каждой библиотекой DLL расширения MFC по очереди во время инициализации. Кроме того, каждый модуль (приложение или обычная библиотека DLL MFC) имеет собственную цепочку объектов **CDynLinkLibrary**.

Чтобы библиотека DLL расширения MFC была подключена к цепочке **CDynLinkLibrary**, она должна создать объект **CDynLinkLibrary** в контексте каждого модуля, использующего библиотеку DLL расширения MFC. Таким образом, если библиотека DLL расширения MFC будет использоваться из обычных библиотек DLL MFC, она должна предоставить экспортированную функцию инициализации, которая создает объект **CDynLinkLibrary**. Каждая обычная библиотека DLL MFC, использующая библиотеку DLL расширения MFC, должна вызывать экспортированную функцию инициализации.

Если библиотека DLL расширения MFC будет использоваться только из приложения MFC (exe) и никогда не будет использоваться из обычной библиотеки DLL MFC, то достаточно создать объект **CDynLinkLibrary** в `DllMain`библиотеки DLL расширения MFC. Это задача кода библиотеки DLL расширения MFC мастера библиотеки DLL MFC. При неявной загрузке библиотеки DLL расширения MFC `DllMain` загружается и выполняется перед запуском приложения. Все созданные **CDynLinkLibrary** собраны в цепочку по умолчанию, которую библиотека DLL MFC резервирует для приложения MFC.

Обратите внимание, что не стоит создавать несколько объектов **CDynLinkLibrary** из одной библиотеки DLL расширения MFC в одной цепочке, особенно если библиотека DLL расширения MFC будет выгружаться из памяти динамически. Не вызывайте функцию инициализации более одного раза из любого модуля.

## <a name="sample-code"></a>Пример кода

В этом примере кода предполагается, что обычная библиотека DLL MFC неявно связывается с библиотекой DLL расширения MFC. Это достигается путем связывания с библиотекой импорта (LIB) библиотеки DLL расширения MFC при сборке обычной библиотеки DLL MFC.

В источнике библиотеки DLL расширения MFC должны находиться следующие строки:

```
// YourExtDLL.cpp:

// standard MFC extension DLL routines
#include "afxdllx.h"

static AFX_EXTENSION_MODULE NEAR extensionDLL = { NULL, NULL };

extern "C" int APIENTRY
DllMain(HINSTANCE hInstance, DWORD dwReason, LPVOID lpReserved)
{
    if (dwReason == DLL_PROCESS_ATTACH)
    {
        // MFC extension DLL one-time initialization
        if (!AfxInitExtensionModule(extensionDLL, hInstance))
           return 0;
    }
    return 1;   // ok
}

// Exported DLL initialization is run in context of
// application or regular MFC DLL
extern "C" void WINAPI InitYourExtDLL()
{
    // create a new CDynLinkLibrary for this app
    new CDynLinkLibrary(extensionDLL);

    // add other initialization here
}
```

Обязательно экспортируйте функцию **InitYourExtDLL**. Это можно сделать с помощью **`__declspec(dllexport)`** или в DEF-файле библиотеки DLL следующим образом:

```
// YourExtDLL.Def:
LIBRARY      YOUREXTDLL
CODE         PRELOAD MOVEABLE DISCARDABLE
DATA         PRELOAD SINGLE
EXPORTS
    InitYourExtDLL
```

Добавьте вызов члена `InitInstance` объекта, производного от `CWinApp`, в каждой обычной библиотеке DLL MFC с помощью библиотеки DLL расширения MFC:

```
// YourRegularDLL.cpp:

class CYourRegularDLL : public CWinApp
{
public:
    virtual BOOL InitInstance(); // Initialization
    virtual int ExitInstance();  // Termination

    // nothing special for the constructor
    CYourRegularDLL(LPCTSTR pszAppName) : CWinApp(pszAppName) { }
};

BOOL CYourRegularDLL::InitInstance()
{
    // any DLL initialization goes here
    TRACE0("YOUR regular MFC DLL initializing\n");

    // wire any MFC extension DLLs into CDynLinkLibrary chain
    InitYourExtDLL();

    return TRUE;
}
```

### <a name="what-do-you-want-to-do"></a>Выберите действие

- [Инициализация библиотеки DLL расширения MFC](run-time-library-behavior.md#initializing-extension-dlls)

- [Инициализация обычных библиотек DLL MFC](run-time-library-behavior.md#initializing-regular-dlls)

### <a name="what-do-you-want-to-know-more-about"></a>Дополнительные сведения

- [Библиотеки DLL расширений MFC](extension-dlls.md)

- [Обычные DLL-библиотеки MFC, статически связанные с MFC](regular-dlls-statically-linked-to-mfc.md)

- [Обычные DLL-библиотеки MFC, динамически связанные с MFC](regular-dlls-dynamically-linked-to-mfc.md)

- [Использование MFC как части библиотеки DLL](../mfc/tn011-using-mfc-as-part-of-a-dll.md)

- [Версия библиотеки DLL MFC](../mfc/tn033-dll-version-of-mfc.md)

## <a name="see-also"></a>См. также

[Библиотеки DLL расширений MFC](extension-dlls.md)
