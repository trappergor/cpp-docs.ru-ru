---
title: С помощью базы данных, OLE и сокетов MFC DLL расширения в обычных библиотеках DLL MFC | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- DLLs [C++], initializing
- DLLs [C++], extension
- DLLs [C++], regular
ms.assetid: 9f1d14a7-9e2a-4760-b3b6-db014fcdb7ff
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: f902f3b512b5684cf185829fdf4346b8851ff8ba
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="using-database-ole-and-sockets-mfc-extension-dlls-in-regular-mfc-dlls"></a>С помощью базы данных, OLE и сокетов MFC DLL расширения в обычных библиотеках DLL MFC
Если при использовании MFC библиотек DLL расширения из обычных библиотек DLL MFC, библиотеки DLL расширения MFC не встроены в **CDynLinkLibrary** объекта цепочки обычной библиотеки DLL MFC, можно запустить в одну или несколько связанных трудностями. Поскольку отладочные версии баз данных MFC, OLE и сокетов поддерживают библиотеки DLL реализованы как библиотека DLL-расширения MFC, может появиться признаки аналогичные проблемы при использовании этих MFC, даже если вы не используете явно любой из собственных библиотека DLL-расширения MFC. Ниже представлены некоторые симптомы:  
  
-   При попытке десериализации объекта типа класса определен в расширении MFC DLL, сообщение «Предупреждение: не удается загрузить окне отслеживания TRACE появляется из архива. Класс не определен.» отображается в окне ТРАССИРОВКИ отладки и объект не удается выполнить сериализацию.  
  
-   Может быть создано исключение, указывающее на недопустимый класс.  
  
-   Ресурсы, хранящиеся в библиотеке DLL расширения MFC не удастся загрузить, так как `AfxFindResourceHandle` возвращает **NULL** или неверный дескриптор ресурса.  
  
-   `DllGetClassObject`, `DllCanUnloadNow`и `UpdateRegistry`, `Revoke`, `RevokeAll`, и `RegisterAll` функциями-членами `COleObjectFactory` не удалось найти фабрику класса, определенные в библиотеке DLL расширения MFC.  
  
-   `AfxDoForAllClasses` не работает с классами в DLL расширений MFC.  
  
-   Стандартной базы данных MFC, сокеты и ресурсы OLE не удалось загрузить. Например **AfxLoadString**(**AFX_IDP_SQL_CONNECT_FAIL**) возвращает пустую строку, даже в том случае, если регулярных DLL MFC должным образом с помощью классов баз данных MFC.  
  
 Решением проблемы является создание и экспорт функции инициализации в расширения MFC библиотеки DLL, которая создает **CDynLinkLibrary** объекта. Эта функция инициализации только один раз, с каждой обычной DLL MFC, используют расширения MFC DLL.  
  
## <a name="mfc-ole-mfc-database-or-dao-or-mfc-sockets-support"></a>MFC OLE, баз данных MFC (или DAO) или поддержка сокеты MFC  
 Если вы используете любой MFC OLE, баз данных MFC (или DAO) или сокеты MFC поддерживает в обычной DLL MFC, соответственно, автоматически связываются отладки MFC расширения MFC DLL MFCOxxD.dll, MFCDxxD.dll и MFCNxxD.dll (где xx — номер версии). Необходимо вызвать предварительно определенную функцию инициализации для каждого из этих библиотек DLL, которые вы используете.  
  
 Для поддержки баз данных, добавьте вызов `AfxDbInitModule` в библиотеку регулярных DLL MFC `CWinApp::InitInstance` функции. Убедитесь, что этот вызов происходит перед любой вызов базового класса или любого добавленного кода, обращающегося к MFCDxxD.dll. Эта функция не принимает никаких параметров и возвращает значение void.  
  
 Для поддержки OLE добавьте вызов `AfxOleInitModule` в библиотеку регулярных DLL MFC `CWinApp::InitInstance`. Обратите внимание, что **COleControlModule InitInstance** вызовов функций `AfxOleInitModule` уже, поэтому, если вы создаете элемента управления OLE и используете `COleControlModule`, не стоит добавлять этот вызов `AfxOleInitModule`.  
  
 Для поддержки сокетов добавьте вызов `AfxNetInitModule` в библиотеку регулярных DLL MFC `CWinApp::InitInstance`.  
  
 Заметьте, что окончательные сборки библиотеки DLL MFC и приложения не используют отдельные библиотеки DLL для базы данных, сокеты, или поддержки OLE. Тем не менее можно безопасно вызывать эти функции инициализации в режиме выпуска.  
  
## <a name="cdynlinklibrary-objects"></a>Объекты CDynLinkLibrary  
 Во время каждой из операций, упомянутых в начале этого раздела MFC должен выполнять поиск необходимого значения или объекта. Например в процессе десериализации MFC должен выполнить поиск по всех доступных классов времени выполнения для сопоставления объектов в архиве с их правильный класс во время выполнения.  
  
 В процессе поиска MFC просматривает все расширения библиотеки DLL MFC используется по цепочке из **CDynLinkLibrary** объектов. **CDynLinkLibrary** объекты автоматически присоединяются к цепочке в процессе их конструирования и создаются каждой библиотеки DLL расширения MFC в свою очередь в ходе инициализации. Кроме того, каждый модуль (приложение или обычной MFC DLL) имеет собственную цепочку **CDynLinkLibrary** объектов.  
  
 Для расширения MFC DLL в **CDynLinkLibrary** цепочки, его необходимо создать **CDynLinkLibrary** объект в контексте каждого модуля, использующего библиотеку DLL расширения MFC. Поэтому, если расширения MFC DLL будет использоваться в обычных библиотеках DLL MFC, необходимо указать экспортированную функцию, которая создает **CDynLinkLibrary** объекта. Каждая обычная библиотека DLL MFC, использующего расширения MFC DLL необходимо вызвать экспортированную функцию.  
  
 Если расширения MFC DLL он будет использоваться из приложения MFC (.exe), а не из обычной DLL MFC, то достаточно для создания **CDynLinkLibrary** объектов в библиотеке MFC DLL расширения `DllMain`. Это делает код библиотеки DLL MFC мастером MFC DLL расширения. При загрузке библиотеки DLL расширения MFC неявно, `DllMain` загружается и выполняется до начала приложения. Любой **CDynLinkLibrary** операции создания соединены в цепочку по умолчанию, с библиотекой DLL MFC резервирует для приложения MFC.  
  
 Обратите внимание, что его не рекомендуется иметь несколько **CDynLinkLibrary** объекты из одной библиотеки DLL расширения MFC в любой цепочке, особенно в том случае, если библиотеки DLL расширения MFC будет динамически выгрузки из памяти. Не вызывайте функцию инициализации более одного раза из одного модуля.  
  
## <a name="sample-code"></a>Пример кода  
 Этот пример кода предполагает неявное связывание регулярных DLL MFC DLL расширений MFC. Это достигается путем связывания с библиотекой импорта (LIB) библиотеки DLL расширения MFC, при построении регулярных DLL MFC.  
  
 Следующие строки должно быть в источнике библиотеки DLL расширения MFC:  
  
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
  
 Добавьте вызов `InitInstance` членом `CWinApp`-производный объект в каждой обычной библиотеке DLL MFC, с помощью библиотеки DLL расширения MFC:  
  
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
  
-   [Инициализация библиотеки DLL расширения MFC](../build/run-time-library-behavior.md#initializing-extension-dlls)  
  
-   [Инициализация обычных библиотек DLL MFC](../build/run-time-library-behavior.md#initializing-regular-dlls)  
  
### <a name="what-do-you-want-to-know-more-about"></a>Дополнительные сведения  
  
-   [Библиотеки DLL расширений MFC](../build/extension-dlls.md)  
  
-   [Обычные DLL-библиотеки MFC, статически связанные с MFC](../build/regular-dlls-statically-linked-to-mfc.md)  
  
-   [Обычные DLL-библиотеки MFC, динамически связанные с MFC](../build/regular-dlls-dynamically-linked-to-mfc.md)  
  
-   [Использование MFC как часть библиотеки DLL](../mfc/tn011-using-mfc-as-part-of-a-dll.md)  
  
-   [Версия библиотеки DLL MFC](../mfc/tn033-dll-version-of-mfc.md)  
  
## <a name="see-also"></a>См. также  
 [Библиотеки DLL расширений MFC](../build/extension-dlls.md)