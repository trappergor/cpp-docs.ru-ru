---
title: С помощью базы данных, OLE и сокетов MFC DLL расширения в обычных библиотеках DLL MFC
ms.date: 11/04/2016
helpviewer_keywords:
- DLLs [C++], initializing
- DLLs [C++], extension
- DLLs [C++], regular
ms.assetid: 9f1d14a7-9e2a-4760-b3b6-db014fcdb7ff
ms.openlocfilehash: 74945f712fed68548e3853d231a586ec0c70d84b
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50587529"
---
# <a name="using-database-ole-and-sockets-mfc-extension-dlls-in-regular-mfc-dlls"></a>С помощью базы данных, OLE и сокетов MFC DLL расширения в обычных библиотеках DLL MFC

При использовании расширения MFC DLL из обычной библиотеки DLL MFC, в том случае, если библиотека DLL расширения MFC не встроены в **CDynLinkLibrary** объект цепочки обычной библиотеки DLL MFC, вы можете столкнуться один или несколько из набора связанных проблем. Так как поддерживает отладочные версии базы данных MFC, OLE и сокетов библиотеки DLL реализованы в виде библиотек DLL расширений MFC, могут возникнуть подобных проблем, если вы используете MFC, эти функции, даже если вы не используете явно любой из собственные библиотеки DLL расширений MFC. Ниже приведены описания некоторых проблем.

- При попытке десериализации объекта типа класса определенные в библиотеки DLL расширения MFC, сообщение «Предупреждение: не удается загрузить окне отслеживания TRACE появляется из архива. Класс не определен.» отображается в окне ТРАССИРОВКИ отладки и объект завершается ошибкой для сериализации.

- Может быть создано исключение, указывающее на недопустимый класс.

- Ресурсы, хранящиеся в библиотеке DLL расширения MFC не удалось загрузить, так как `AfxFindResourceHandle` возвращает **NULL** или неверный дескриптор ресурса.

- `DllGetClassObject`, `DllCanUnloadNow`и `UpdateRegistry`, `Revoke`, `RevokeAll`, и `RegisterAll` функциями-членами `COleObjectFactory` не удалось найти фабрику класса, определенные в библиотеке DLL расширения MFC.

- `AfxDoForAllClasses` не работает с классами в библиотеки DLL расширения MFC.

- Стандартной базы данных MFC, сокеты и ресурсы OLE не удалось загрузить. Например **AfxLoadString**(**AFX_IDP_SQL_CONNECT_FAIL**) возвращает пустую строку, даже в том случае, если обычной библиотеки DLL MFC правильно использует классы баз данных MFC.

Решение этих проблем является создание и экспорт функции инициализации в библиотеке DLL, который создает расширения MFC **CDynLinkLibrary** объекта. Вызывайте эту функцию для инициализации, точно в том случае, когда из каждой обычной библиотеки DLL MFC, использующий библиотеки DLL расширения MFC.

## <a name="mfc-ole-mfc-database-or-dao-or-mfc-sockets-support"></a>MFC OLE, баз данных MFC (или DAO) или поддержки сокетов MFC

Если вы используете любой MFC OLE, MFC базы данных (или DAO) или сокетов MFC поддерживает в обычной библиотеки DLL MFC, соответственно, автоматически связываются MFC отладки расширения MFC DLL MFCOxxD.dll, MFCDxxD.dll и MFCNxxD.dll (где xx — номер версии). Предварительно определенную функцию инициализации необходимо вызвать для каждого из этих библиотек DLL, которые вы используете.

Для поддержки баз данных, добавьте вызов `AfxDbInitModule` в библиотеку регулярных DLL MFC `CWinApp::InitInstance` функции. Убедитесь, что этот вызов происходит перед любой вызов базового класса или любого добавленного кода, обращающегося к MFCDxxD.dll. Эта функция не принимает никаких параметров и возвращает значение void.

Для поддержки OLE добавьте вызов `AfxOleInitModule` в библиотеку регулярных DLL MFC `CWinApp::InitInstance`. Обратите внимание, что **COleControlModule InitInstance** вызовы функций `AfxOleInitModule` уже, поэтому, если вы создаете управления OLE и используете `COleControlModule`, не следует добавлять этот вызов `AfxOleInitModule`.

Для поддержки сокетов добавьте вызов `AfxNetInitModule` в библиотеку регулярных DLL MFC `CWinApp::InitInstance`.

Обратите внимание, что окончательные сборки DLL-библиотеки MFC и приложения не используют отдельные библиотеки DLL для базы данных, сокеты, или поддерживает OLE. Тем не менее можно безопасно вызывать эти функции инициализации в режиме выпуска.

## <a name="cdynlinklibrary-objects"></a>Объекты CDynLinkLibrary

Во время каждой из операций, упомянутых в начале этого раздела MFC должна найти нужное значение или объект. Например во время десериализации MFC должен выполнить поиск по всех доступных классов времени выполнения для сопоставления объектов в архив с их правильный класс времени выполнения.

В ходе поиска MFC просматривает все библиотеки DLL расширения MFC используется по цепочке из **CDynLinkLibrary** объектов. **CDynLinkLibrary** объекты автоматически присоединяются к цепочке в процессе их конструирования и создаются каждой библиотеки DLL расширения MFC в свою очередь в ходе инициализации. Кроме того, каждый модуль (приложение или обычная библиотека DLL MFC) имеет собственную цепочку из **CDynLinkLibrary** объектов.

Для расширения MFC DLL в **CDynLinkLibrary** цепочки, его необходимо создать **CDynLinkLibrary** объект в контексте каждого модуля, использующего библиотеку DLL расширения MFC. Таким образом, если расширения MFC DLL будет использоваться из обычных библиотек DLL MFC, он должен предоставлять экспортированную функцию, которая создает **CDynLinkLibrary** объекта. Каждая обычная библиотека DLL MFC, MFC с расширением DLL необходимо вызвать экспортированную функцию.

Если расширения MFC DLL он будет использоваться из приложения MFC (.exe), а не из обычной библиотеки DLL MFC, то этого достаточно для создания **CDynLinkLibrary** объекта в библиотеке MFC DLL расширения `DllMain`. Это и делает код библиотеки DLL расширения MFC мастера MFC DLL. При загрузке библиотеки DLL расширения MFC неявно, `DllMain` загружает и выполняет их до выполнения приложения. Любой **CDynLinkLibrary** созданий соединены в цепочку по умолчанию, что библиотеки DLL MFC резервирует для приложения MFC.

Обратите внимание на то, что его не рекомендуется иметь несколько **CDynLinkLibrary** объектов из одной библиотеки DLL расширения MFC в любой цепочке, особенно в том случае, если библиотека DLL расширения MFC будет динамически выгружаться из памяти. Не вызывайте функцию инициализации более одного раза из одного модуля.

## <a name="sample-code"></a>Пример кода

В этом примере кода предполагается, что обычной библиотеки DLL MFC неявно связывание с библиотекой DLL расширения MFC. Это достигается путем связывания с библиотекой импорта (LIB), библиотеки DLL расширения MFC, при создании обычной библиотеки DLL MFC.

Следующие строки должен быть в источник библиотеки DLL расширения MFC:

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

Не забудьте экспортировать **InitYourExtDLL** функции. Это можно сделать с помощью **__declspec(dllexport)** или в DEF-файле библиотеки DLL, как показано ниже:

```
// YourExtDLL.Def:
LIBRARY      YOUREXTDLL
CODE         PRELOAD MOVEABLE DISCARDABLE
DATA         PRELOAD SINGLE
EXPORTS
    InitYourExtDLL
```

Добавьте вызов `InitInstance` членом `CWinApp`-объект в каждой обычной библиотеке DLL MFC, с помощью библиотеки DLL расширения MFC, производной от:

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

- [Инициализация библиотеки DLL расширения MFC](../build/run-time-library-behavior.md#initializing-extension-dlls)

- [Инициализация обычных библиотек DLL MFC](../build/run-time-library-behavior.md#initializing-regular-dlls)

### <a name="what-do-you-want-to-know-more-about"></a>Дополнительные сведения

- [Библиотеки DLL расширений MFC](../build/extension-dlls.md)

- [Обычные DLL-библиотеки MFC, статически связанные с MFC](../build/regular-dlls-statically-linked-to-mfc.md)

- [Обычные DLL-библиотеки MFC, динамически связанные с MFC](../build/regular-dlls-dynamically-linked-to-mfc.md)

- [Использование MFC как часть библиотеки DLL](../mfc/tn011-using-mfc-as-part-of-a-dll.md)

- [Версия библиотеки DLL MFC](../mfc/tn033-dll-version-of-mfc.md)

## <a name="see-also"></a>См. также

[Библиотеки DLL расширений MFC](../build/extension-dlls.md)