---
title: "Использование библиотек DLL расширения баз данных, OLE и сокетов в обычных библиотеках DLL | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "DLL-библиотеки [C++], расширение"
  - "DLL-библиотеки [C++], инициализация"
  - "DLL-библиотеки [C++], обычный"
ms.assetid: 9f1d14a7-9e2a-4760-b3b6-db014fcdb7ff
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Использование библиотек DLL расширения баз данных, OLE и сокетов в обычных библиотеках DLL
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

При использовании библиотек DLL расширения из обычных библиотек DLL, если библиотеки DLL расширения не встроены в цепочку объектов **CDynLinkLibrary** обычной библиотеки DLL, можно столкнуться с одной или несколькими взаимосвязанными трудностями.  Поскольку отладочные версии библиотек DLL поддержки баз данных MFC, OLE и сокетов реализованы как DLL расширения, подобные трудности могут возникнуть, если используются эти функции MFC, даже когда не используется явно какая\-либо из собственных DLL\-библиотек расширения.  Ниже представлены некоторые симптомы.  
  
-   При попытке выполнения десериализации объекта типа класса, определенного в библиотеке DLL расширения, в окне отслеживания TRACE появляется сообщение "Предупреждение. Невозможно загрузить CyourClass из архива.  Класс не определен." и сериализация объекта не выполняется.  
  
-   Может появиться исключение, указывающее на недопустимый класс.  
  
-   Ресурсы, хранящиеся в DLL\-библиотеке расширения, не удается загрузить, поскольку `AfxFindResourceHandle` возвращает **NULL** или неверный дескриптор ресурса.  
  
-   `DllGetClassObject`, `DllCanUnloadNow`, и `UpdateRegistry`, `Revoke`, `RevokeAll`, а также функции\-члены `RegisterAll` объекта `COleObjectFactory` не могут найти фабрику класса, определенное в библиотеке DLL расширения.  
  
-   `AfxDoForAllClasses` не работает с классами в DLL\-библиотеке расширения.  
  
-   Не загружаются ресурсы стандартной базы данных MFC, сокетов или OLE.  Например, **AfxLoadString**\(**AFX\_IDP\_SQL\_CONNECT\_FAIL**\) возвращает пустую строку, даже когда обычная библиотека DLL корректно использует классы базы данных MFC.  
  
 Решением проблемы может быть создание и экспорт функции инициализации в DLL\-библиотеке расширения, которая создает объект **CDynLinkLibrary**.  Выполните вызов этой функции инициализации по одному разу из каждой обычной библиотеки DLL, использующей DLL\-библиотеку расширения.  
  
## Поддержка базы данных MFC OLE, MFC \(или DAO\) или сокетов MFC  
 Если используется поддержка MFC OLE, базы данных MFC \(или DAO\), или же сокетов MFC в обычной библиотеке DLL, то отладочные библиотеки DLL расширения MFC MFCOxxD.dll, MFCDxxD.dll и MFCNxxD.dll соответственно \(где xx — номер версии\) связываются автоматически.  Необходимо вызвать предварительно определенную функцию инициализации для каждой из используемых библиотек DLL.  
  
 Для поддержки баз данных добавьте вызов `AfxDbInitModule` к функции `CWinApp::InitInstance` обычной библиотеки DLL.  Убедитесь, что вызов имеет место до любого вызова основного класса или любого добавленного кода, обращающегося к MFCDxxD.dll.  Эта функция не получает никаких параметров и возвращает значение void.  
  
 Для поддержки OLE добавьте вызов `AfxOleInitModule` к функции `CWinApp::InitInstance` обычной библиотеки DLL.  Следует отметить, что функция **COleControlModule InitInstance** уже вызывает `AfxOleInitModule`, поэтому при построении элемента управления OLE и использовании `COleControlModule` добавлять этот вызов в `AfxOleInitModule` не нужно.  
  
 Для поддержки сокетов добавьте вызов `AfxNetInitModule` к функции `CWinApp::InitInstance` обычной библиотеки DLL.  
  
 Обратите внимание, что окончательные построения библиотек DLL и приложений MFC не используют отдельные библиотеки DLL для поддержки баз данных, сокетов или OLE.  Однако надежнее выполнять вызов этих функций инициализации в режиме выпуска.  
  
## Объекты CDynLinkLibrary  
 В ходе каждой из упомянутых в начале этого раздела операций MFC должен выполнять поиск необходимого значения или объекта.  Например, в процессе десериализации MFC должен выполнить поиск по всем доступным в данный момент классам времени выполнения для сопоставления объектов в архиве с соответствующими классами времени выполнения.  
  
 В процессе поиска MFC просматривает все используемые библиотеки DLL расширения, следуя по цепочке объектов **CDynLinkLibrary**.  Объекты **CDynLinkLibrary** автоматически присоединяются к цепочке в процессе их конструирования и создаются каждой из библиотек DLL расширения в свою очередь в ходе инициализации.  Кроме того, каждый модуль \(приложение или обычная библиотека DLL\) имеет собственную цепочку объектов **CDynLinkLibrary**.  
  
 Чтобы включить библиотеку DLL расширения в цепочку **CDynLinkLibrary**, эта библиотека должна создать объект **CDynLinkLibrary** в контексте каждого модуля, использующего библиотеку DLL расширения.  Таким образом, если DLL\-библиотеку расширения планируется использовать из обычных библиотек DLL, она должна предоставлять экспортированную функцию, создающую объект **CDynLinkLibrary**.  Каждая обычная библиотека DLL, использующая библиотеку DLL расширения, должна вызывать экспортируемую функцию инициализации.  
  
 Если библиотеку DLL расширения планируется использовать только из приложения MFC \(EXE\), а не из обычной библиотеки DLL, то достаточно создать объект **CDynLinkLibrary** в модуле `DllMain` DLL\-библиотеки расширения.  Именно это и делает код библиотеки DLL расширения мастера библиотек DLL MFC.  При неявной загрузке библиотеки DLL расширения, `DllMain` загружается и выполняется до начала выполнения приложения.  Все созданные объекты **CDynLinkLibrary** включаются в цепочку по умолчанию, которую DLL\-библиотека MFC резервирует для приложения MFC.  
  
 Следует обратить внимание на то, что не рекомендуется иметь несколько объектов **CDynLinkLibrary** из одной библиотеки DLL расширения в любой цепочке, особенно если DLL\-библиотека расширения предназначена для динамической выгрузки из памяти.  Не вызывайте функцию инициализации более одного раза из одного модуля.  
  
## Пример кода  
 В этом примере кода предполагается, что обычная библиотека DLL неявно связана с библиотекой DLL расширения.  Это осуществляется путем связывания с библиотекой импорта \(LIB\) библиотеки DLL расширения при создании обычной библиотеки DLL.  
  
 В исходном коде библиотеки DLL расширения должны присутствовать приведенные ниже строки:  
  
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
        // extension DLL one-time initialization  
        if (!AfxInitExtensionModule(extensionDLL, hInstance))  
           return 0;  
    }  
    return 1;   // ok  
}  
  
// Exported DLL initialization is run in context of  
// application or regular DLL  
extern "C" void WINAPI InitYourExtDLL()  
{  
    // create a new CDynLinkLibrary for this app  
    new CDynLinkLibrary(extensionDLL);  
  
    // add other initialization here  
}  
```  
  
 Убедитесь в том, что функция **InitYourExtDLL** экспортирована.  Это можно сделать с помощью ключевого слова **\_\_declspec\(dllexport\)** или непосредственно в DEF\-файле библиотеки DLL, как показано ниже:  
  
```  
// YourExtDLL.Def:  
LIBRARY      YOUREXTDLL  
CODE         PRELOAD MOVEABLE DISCARDABLE  
DATA         PRELOAD SINGLE  
EXPORTS  
    InitYourExtDLL  
```  
  
 Добавьте вызов члена `InitInstance` объекта, производного от класса `CWinApp`, в каждой обычной библиотеке DLL, используя библиотеку DLL расширения:  
  
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
    TRACE0("YOUR regular DLL initializing\n");  
  
    // wire any extension DLLs into CDynLinkLibrary chain  
    InitYourExtDLL();  
  
    return TRUE;  
}  
```  
  
### Выберите действие.  
  
-   [Инициализация библиотеки \(DLL\) расширения](../build/initializing-extension-dlls.md)  
  
-   [Инициализация обычных библиотек DLL](../Topic/Initializing%20Regular%20DLLs.md)  
  
### Дополнительные сведения  
  
-   [Библиотеки DLL расширения](../build/extension-dlls.md)  
  
-   [Обычные библиотеки DLL, статически компонуемые с MFC](../build/regular-dlls-statically-linked-to-mfc.md)  
  
-   [Обычные библиотеки DLL, динамически связываемые с MFC](../Topic/Regular%20DLLs%20Dynamically%20Linked%20to%20MFC.md)  
  
-   [Использование MFC как части библиотеки DLL](../mfc/tn011-using-mfc-as-part-of-a-dll.md)  
  
-   [Версия библиотеки DLL MFC](../mfc/tn033-dll-version-of-mfc.md)  
  
## См. также  
 [Библиотеки DLL расширения](../build/extension-dlls.md)