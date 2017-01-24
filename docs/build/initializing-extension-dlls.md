---
title: "Инициализация библиотек расширения | Microsoft Docs"
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
  - "библиотека DLL - расширения [C++], инициализация"
  - "инициализация библиотек DLL"
ms.assetid: 08ad0381-3808-4bea-a93c-c9ba62496543
caps.latest.revision: 10
caps.handback.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Инициализация библиотек расширения
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Поскольку в библиотеках расширения, в отличие от обычных библиотек DLL, не используется производный от `CWinApp` объект, следует добавить код инициализации и завершения в функцию `DllMain`, созданную с помощью мастера DLL MFC.  
  
 C помощью мастера автоматически создается следующий код библиотеки расширения.  В приведенном ниже коде вместо `PROJNAME` следует использовать имя создаваемого проекта.  
  
```  
#include "stdafx.h"  
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
  
      // Extension DLL one-time initialization  
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
  
 За счет создания нового объекта **CDynLinkLibrary** во время инициализации обеспечивается экспорт объектов `CRuntimeClass` или ресурсов из библиотеки расширения в клиентское приложение.  
  
 Если предполагается использование библиотеки расширения в одной или нескольких обычных библиотеках DLL, необходимо экспортировать функцию, с помощью которой создается объект **CDynLinkLibrary**.  Эту функцию необходимо вызывать в каждой из обычных библиотек, в которых используется библиотека расширения.  Чтобы использовать классы и функции, экспортированные из библиотеки расширения, необходимо вызвать эту функцию инициализации в функции\-члене `InitInstance` объекта, производного от класса `CWinApp` обычной библиотеки DLL.  
  
 В функции `DllMain`, автоматически создаваемой с помощью мастера DLL MFC, при обращении к функции `AfxInitExtensionModule` регистрируются классы времени выполнения модуля \(структуры `CRuntimeClass`\), а также производства объектов \(объекты `COleObjectFactory`\), которые используются при создании объекта **CDynLinkLibrary**.  Проверьте значение, возвращаемое функцией `AfxInitExtensionModule`. Если функция `AfxInitExtensionModule` возвращает нулевое значение, в функции `DllMain` также следует возвратить нулевое значение.  
  
 Если библиотека расширения явно связана с исполняемым файлом \(то есть в исполняемом файле вызывается функция `AfxLoadLibrary` для связывания с библиотекой DLL\), следует добавить вызов функции `AfxTermExtensionModule` со значением **DLL\_PROCESS\_DETACH**.  Эта функция используется в MFC для очистки библиотеки расширения после отсоединения от нее всех процессов \(выполняется при завершении процесса или выгрузке библиотеки DLL с помощью функции `AfxFreeLibrary`\).  В случае неявного связывания библиотеки расширения с приложением вызывать функцию `AfxTermExtensionModule` не требуется.  
  
 В приложениях, явно связанных с библиотеками расширения, при освобождении библиотеки следует вызвать функцию **AfxTermExtensionModule**.  Если в таком приложении используется несколько потоков, следует вызвать функции `AfxLoadLibrary` и `AfxFreeLibrary` \(вместо функций Win32 **LoadLibrary** и **FreeLibrary**\).  При использовании функций `AfxLoadLibrary` и `AfxFreeLibrary` гарантируется, что выполнение кода запуска и завершения работы при загрузке и выгрузке библиотеки расширения, не приведет к повреждению глобального состояния MFC.  
  
 Поскольку на момент вызова функции `DllMain` инициализация библиотеки MFCx0.dll полностью завершается, можно выделить память и вызвать функции MFC в функции `DllMain` \(в отличие от 16\-разрядной версии MFC\).  
  
 В библиотеках расширения многопоточность реализуется за счет обработки значений **DLL\_THREAD\_ATTACH** и **DLL\_THREAD\_DETACH** функции `DllMain`.  Эти значения передаются в функцию `DllMain` в случае присоединения потоков к библиотеке DLL и отсоединения от нее соответственно.  Чтобы обеспечить хранение в библиотеке DLL индексов локальной памяти потока \(TLS\) для каждого присоединенного к ней потока, вызовите функцию [TlsAlloc](http://msdn.microsoft.com/library/windows/desktop/ms686801) в процессе присоединения библиотеки DLL.  
  
 Обратите внимание, что в файле заголовка Afxdllx.h содержатся специальные определения для структур, используемых в библиотеках расширения, например `AFX_EXTENSION_MODULE` и **CDynLinkLibrary**.  Этот файл заголовка необходимо включить в библиотеку расширения.  
  
> [!NOTE]
>  Обратите внимание, что в файле Stdafx.h не допускается определение или отмена определения каких\-либо макросов \_AFX\_NO\_XXX.  Дополнительные сведения см. в статье базы знаний "PRB. Проблемы, возникающие при определении \_AFX\_NO\_XXX" \(на английском языке, ИД статьи — 140751\).  Статьи базы знаний можно найти в библиотеке MSDN или с [http:\/\/search.support.microsoft.com\/](http://search.support.microsoft.com/).  
  
 Пример функции инициализации, в которой реализуется обработка многопоточности, см. в разделе [Использование локальной памяти потока в библиотеке DLL](http://msdn.microsoft.com/library/windows/desktop/ms686997) в пакете [!INCLUDE[winsdkshort](../atl/reference/includes/winsdkshort_md.md)].  Обратите внимание, что в примере используется функция точки входа **LibMain**, которой следует присвоить имя `DllMain`, что позволит использовать ее в библиотеках времени выполнения MFC и C.  
  
 В примере MFC [DLLHUSK](http://msdn.microsoft.com/ru-ru/dfcaa6ff-b8e2-4efd-8100-ee3650071f90) показан порядок использования функций инициализации.  
  
## Выберите действие.  
  
-   [Инициализация обычных библиотек DLL](../Topic/Initializing%20Regular%20DLLs.md)  
  
-   [Инициализация библиотек DLL, не относящихся к MFC](../Topic/Initializing%20Non-MFC%20DLLs.md)  
  
## Дополнительные сведения  
  
-   [Поведение библиотеки времени выполнения языка C и функция \_DllMainCRTStartup](../build/run-time-library-behavior.md)  
  
-   [Использование библиотек DLL расширения баз данных, OLE и сокетов в обычных библиотеках DLL](../build/using-database-ole-and-sockets-extension-dlls-in-regular-dlls.md)  
  
-   [\<caps:sentence id\="tgt34" sentenceid\="58bb7328659bda9ffb73a1dcd39da06b" class\="tgtSentence"\>Спецификация функции DllMain \(Windows SDK\)\<\/caps:sentence\>](http://msdn.microsoft.com/library/windows/desktop/ms682583)  
  
-   [\<caps:sentence id\="tgt35" sentenceid\="f29344705c59343b34b642944921cbdf" class\="tgtSentence"\>Функция точки входа библиотеки динамической компоновки \(Windows SDK\)\<\/caps:sentence\>](http://msdn.microsoft.com/library/windows/desktop/ms682596)  
  
## См. также  
 [Инициализация библиотеки DLL](../build/initializing-a-dll.md)