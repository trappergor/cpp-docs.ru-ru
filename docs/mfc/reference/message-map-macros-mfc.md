---
title: "Сообщение макросы схемы (MFC) | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vc.mfc.messages
dev_langs:
- C++
helpviewer_keywords:
- message map macros
- Windows messages [C++], declaration
- demarcating Windows messages
- message maps [C++], macros
- message maps [C++], declaration and demarcation
- message mapping macros
- ranges, message map
- message map ranges
ms.assetid: 531b15ce-32b5-4ca0-a849-bb519616c731
caps.latest.revision: 10
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
translationtype: Machine Translation
ms.sourcegitcommit: d4b97ed874b145f9c6d9a9536476243bba0fd1c1
ms.openlocfilehash: 0c5856dce919ca8ea2d396fbf2523dc45409b519
ms.lasthandoff: 03/06/2017

---
# <a name="message-map-macros-mfc"></a>Макросы схемы сообщений (MFC)
Для поддержки схемы сообщений, MFC предоставляет следующие макросы:  
  
### <a name="message-map-declaration-and-demarcation-macros"></a>Объявление схемы сообщений и определение границ макросы  
  
|||  
|-|-|  
|[DECLARE_MESSAGE_MAP](#declare_message_map)|Объявляет, что схема сообщений будет использоваться в классе сопоставление сообщений с функциями (необходимо использовать в объявлении класса).|  
|[BEGIN_MESSAGE_MAP](#begin_message_map)|Начинается определение схемы сообщений (необходимо использовать реализацию класса).|  
|[END_MESSAGE_MAP](#end_message_map)|Завершает определение схемы сообщений (необходимо использовать реализацию класса).|  
  
### <a name="message-mapping-macros"></a>Макросы сопоставления сообщений  
  
|||  
|-|-|  
|[ON_COMMAND](#on_command)|Указывает, какая функция будет обрабатывать сообщения указанную команду.|  
|[ON_CONTROL](#on_control)|Указывает, какая функция будет обрабатывать сообщения уведомление указанного элемента управления.|  
|[ON_MESSAGE](#on_message)|Указывает, какая функция будет обрабатывать определенное пользователем сообщение.|  
|[ON_OLECMD](#on_olecmd)|Указывает, какая функция будет обрабатывать команду меню из DocObject или его контейнера.|  
|[ON_REGISTERED_MESSAGE](#on_registered_message)|Указывает, какая функция будет обрабатывать зарегистрированных пользователем сообщение.|  
|[ON_REGISTERED_THREAD_MESSAGE](#on_registered_thread_message)|Указывает, какая функция будет обрабатывать зарегистрированных определяемых пользователем сообщений, при наличии `CWinThread` класса.|  
|[ON_THREAD_MESSAGE](#on_thread_message)|Указывает, какая функция будет обрабатывать определенное пользователем сообщение при наличии `CWinThread` класса.|  
|[ON_UPDATE_COMMAND_UI](#on_update_command_ui)|Указывает, какая функция будет обрабатывать сообщения команды обновления указанного пользовательского интерфейса.|  
  
### <a name="message-map-range-macros"></a>Макросы схемы сообщений диапазона  
  
|||  
|-|-|  
|[ON_COMMAND_RANGE](#on_command_range)|Указывает, какую функцию обработки диапазона идентификаторов команд, указанных в первые два параметра в макрос.|  
|[ON_UPDATE_COMMAND_UI_RANGE](#on_update_command_ui_range)|Указывает, какой обработчик обновление будет обрабатывать диапазона идентификаторов команд, указанных в первых двух pa] араметры в макрос.|  
|[ON_CONTROL_RANGE](#on_control_range)|Указывает, какие функции будут обрабатывать уведомления из диапазона идентификаторов, указанных в качестве второго и третьего параметров для макроса элемента управления. Первый параметр является сообщение уведомления элемента управления, таких как **BN_CLICKED**.|  
  
 Дополнительные сведения о схемы сообщений, объявление схемы сообщений и определение границ макросы и макросы сопоставления сообщений см. [схемы сообщений](../../mfc/reference/message-maps-mfc.md) и [обработка сообщений и разделы сопоставления](../../mfc/message-handling-and-mapping.md). Дополнительные сведения о диапазонах схемы сообщений в разделе [обработчики для диапазонов схем сообщений](../../mfc/handlers-for-message-map-ranges.md).  

## <a name="declare_message_map"></a>DECLARE_MESSAGE_MAP
 Объявляет, что класс определяет схему сообщений. Каждый `CCmdTarget`-производного класса в приложении необходимо указать схему сообщений для обработки сообщений.  
  
### <a name="syntax"></a>Синтаксис  
  
```    
DECLARE_MESSAGE_MAP( )  
```  
  
### <a name="remarks"></a>Примечания  
 Используйте `DECLARE_MESSAGE_MAP` макрос в конце объявления класса. В CPP-файле, который определяет функции-члены класса, используйте `BEGIN_MESSAGE_MAP` макрос, макрос операции для каждого обработчика сообщений функций и `END_MESSAGE_MAP` макрос.  
  
> [!NOTE]
>  При объявлении любого элемента после `DECLARE_MESSAGE_MAP`, необходимо указать новый тип доступа (**открытый**, `private`, или `protected`) для них.  
  
 Дополнительные сведения о сообщении сопоставляет и `DECLARE_MESSAGE_MAP` макрос, в разделе [обработка сообщений и сопоставление разделов](../../mfc/message-handling-and-mapping.md).  
  
### <a name="example"></a>Пример  
```cpp  
class CMainFrame : public CMDIFrameWnd
{
   DECLARE_MESSAGE_MAP()

   // Remainder of class declaration omitted.
``` 
  
### <a name="requirements"></a>Требования  
 **Заголовок:** afxwin.h  

## <a name="begin_message_map"></a>BEGIN_MESSAGE_MAP
Начинается определение карту сообщения.  
  
### <a name="syntax"></a>Синтаксис  
  
```  
BEGIN_MESSAGE_MAP( theClass, baseClass )  
```  
  
### <a name="parameters"></a>Параметры  
 `theClass`  
 Указывает имя класса, сообщение которого сопоставления.  
  
 `baseClass`  
 Указывает имя базового класса `theClass`.  
  
### <a name="remarks"></a>Примечания  
 В файле реализации (CPP), который определяет функции-члены класса, запустить сопоставление сообщений с `BEGIN_MESSAGE_MAP` макрос, затем добавить макрос записи для каждой из функций обработчика сообщений и выполните сопоставление сообщений с `END_MESSAGE_MAP` макрос.  
  
 Дополнительные сведения о схемах сообщений см. в разделе [схемы сообщений](message-maps-mfc.md)  
  
### <a name="example"></a>Пример  
```cpp  
BEGIN_MESSAGE_MAP(CMainFrame, CMDIFrameWnd)
   ON_WM_CREATE()
END_MESSAGE_MAP()
```
  
### <a name="requirements"></a>Требования  
 **Заголовок:** afxwin.h 

## <a name="end_message_map"></a>END_MESSAGE_MAP
Завершает определение карту сообщения.  
  
### <a name="syntax"></a>Синтаксис  
  
```   
END_MESSAGE_MAP( )  
```  
  
### <a name="remarks"></a>Примечания  
 Дополнительные сведения о сообщении сопоставляет и `END_MESSAGE_MAP` макрос, в разделе [обработка сообщений и сопоставление разделов](../../mfc/message-handling-and-mapping.md).  
  
### <a name="requirements"></a>Требования  
 **Заголовок:** afxwin.h  

## <a name="on_command"></a>ON_COMMAND
Этот макрос сопоставляет сообщение команды функции-члена.  
  
### <a name="syntax"></a>Синтаксис  
  
```  
ON_COMMAND( id, memberFxn )  
```  
  
### <a name="parameters"></a>Параметры  
 `id`  
 Идентификатор команды.  
  
 `memberFxn`  
 Имя функции обработчика сообщений, с которым сопоставлен команды.  
  
### <a name="remarks"></a>Примечания  
 Он указывает, какая функция будет обрабатывать сообщения команды из пользовательского интерфейса объект command, такие как кнопки панели инструментов или элемента меню.  
  
 Когда команда целевой объект получает Windows **WM_COMMAND** сообщение с указанным Идентификатором `ON_COMMAND` будет вызывать функцию-член `memberFxn` для обработки сообщения.  
  
 Используйте `ON_COMMAND` для сопоставления одной команды к функции-члену. Используйте [ON_COMMAND_RANGE](#on_command_range) для сопоставления диапазона идентификаторов команд один член функции. Только одна запись сопоставления сообщений можно сопоставить идентификатор данной команды. То есть не удается сопоставить несколько обработчиков команды. Дополнительные сведения и примеры см. в разделе [обработка сообщений и сопоставление разделов](../../mfc/message-handling-and-mapping.md).  
  
### <a name="example"></a>Пример  
```cpp  
BEGIN_MESSAGE_MAP(CMFCListViewDoc, CDocument)
   ON_COMMAND(ID_MYCOMMAND, &CMFCListViewDoc::OnMycommand)
END_MESSAGE_MAP()
``` 
  
### <a name="requirements"></a>Требования  
 **Заголовок:** afxmsg_.h  
  
## <a name="on_control"></a>ON_CONTROL
Указывает, какие функции будет обрабатывать сообщения пользовательского уведомления.  
  
### <a name="syntax"></a>Синтаксис  
  
```  
ON_CONTROL( wNotifyCode, id, memberFxn )  
```  
  
### <a name="parameters"></a>Параметры  
 `wNotifyCode`  
 Код уведомления элемента управления.  
  
 `id`  
 Идентификатор команды.  
  
 `memberFxn`  
 Имя функции обработчика сообщений, с которым сопоставлен команды.  
  
### <a name="remarks"></a>Примечания  
 Сообщения уведомления элемента управления, отправленными из элемента управления в его родительского окна.  
  
 Должно быть ровно один `ON_CONTROL` инструкции макроса карты сообщений для каждого сообщения уведомления элемента управления, должен быть сопоставлен функцию обработки сообщений.  
  
 Дополнительные сведения и примеры см. в разделе [обработка сообщений и сопоставление разделов](../../mfc/message-handling-and-mapping.md).  
  
### <a name="requirements"></a>Требования  
 **Заголовок:** afxmsg_.h  
  

## <a name="on_message"></a>ON_MESSAGE  
Указывает, какая функция будет обрабатывать определенное пользователем сообщение.  
  
### <a name="syntax"></a>Синтаксис  
  
```  
ON_MESSAGE( message, memberFxn )  
```  
  
### <a name="parameters"></a>Параметры  
 `message`  
 Идентификатор сообщения.  
  
 `memberFxn`  
 Имя функции обработчика сообщений, с которым сопоставляется сообщение.  
  
 Тип функции должен быть `afx_msg LRESULT (CWnd::*)(WPARAM, LPARAM)`.  
  
### <a name="remarks"></a>Примечания  
 Определяемые пользователем сообщения, все сообщения, которые не являются стандартные `WM_MESSAGE` сообщений. При выборе идентификатор сообщения, необходимо использовать значения в диапазоне от `WM_USER` (0x0400) для 0x7FFF или `WM_APP` (0x8000) для 0xBFFF. Дополнительные сведения об ИД сообщений в разделе [WM_APP](http://msdn.microsoft.com/library/windows/desktop/ms644930).  
  
 Должно быть ровно один `ON_MESSAGE` инструкции макроса в сопоставлении сообщения для каждого определяемого пользователем сообщения должен быть сопоставлен функцию обработки сообщений.  
  
> [!NOTE]
>  Помимо определяемых пользователем сообщений `ON_MESSAGE` обрабатывает сообщения Windows, реже. Дополнительные сведения см. статью базы знаний [99848: INFO: используйте макрос ON_MESSAGE() карты менее типичные сообщения](http://go.microsoft.com/fwlink/?linkId=192022).  
  
 Дополнительные сведения и примеры см. в разделе [обработка сообщений и сопоставление разделов](../../mfc/message-handling-and-mapping.md) и [определяемые пользователем обработчики](user-defined-handlers.md)  
  
### <a name="example"></a>Пример  
```cpp  
#define WM_MYMESSAGE (WM_USER + 100)

BEGIN_MESSAGE_MAP(CMyWnd2, CWnd)
   ON_MESSAGE(WM_MYMESSAGE, OnMyMessage)
END_MESSAGE_MAP()

// inside the class declaration
 afx_msg LRESULT OnMyMessage(WPARAM wParam, LPARAM lParam);

 LRESULT CMyWnd2::OnMyMessage(WPARAM wParam, LPARAM lParam)
{
   UNREFERENCED_PARAMETER(wParam);
   UNREFERENCED_PARAMETER(lParam);

   // Handle message here. 

   return 0;
}
```   
  
### <a name="requirements"></a>Требования  
 **Заголовок:** afxmsg_.h  

## <a name="on_olecmd"></a>ON_OLECMD    
Направляет команды через интерфейс диспетчеризации командной `IOleCommandTarget`.  
  
### <a name="syntax"></a>Синтаксис  
  
```  
ON_OLECMD( pguid, olecmdid, id )  
```  
  
### <a name="parameters"></a>Параметры  
 `pguid`  
 Идентификатор группы команд, к которой принадлежит команда. Используйте **NULL** стандартные группы.  
  
 *olecmdid*  
 Идентификатор команды OLE.  
  
 `id`  
 Идентификатор меню, панели инструментов идентификатор, button ID или другой идентификатор ресурса или объекта, выполнив команду.  
  
### <a name="remarks"></a>Примечания  
 `IOleCommandTarget`позволяет контейнера для получения команд, которые создаются в пользовательском интерфейсе DocObject, а также контейнер для отправки те же команды (такие как новый, открыть, сохранить как и печати в меню "файл"; и скопируйте, вставьте, отменить, и так далее, в меню Правка) для DocObject.  
  
 `IOleCommandTarget`Это проще, чем OLE-автоматизации `IDispatch`. `IOleCommandTarget`полностью зависит от стандартного набора команд, редко бывает аргументы и задействован никакой информации о типе (безопасность типа позволяет уменьшить также аргументы командной строки). Если требуется отправить команды с аргументами, используйте [COleServerDoc::OnExecOleCmd](coleserverdoc-class.md#onexecolecmd).  
  
 `IOleCommandTarget` Команд стандартного меню с MFC в реализованы следующие макросы:  
  
 **(ON_OLECMD_CLEARSELECTION)**  
  
 Отправляет команду Изменить очистить. Реализованы в виде:  
  
 `ON_OLECMD(NULL, OLECMDID_CLEARSELECTION, ID_EDIT_CLEAR)`  
  
 **(ON_OLECMD_COPY)**  
  
 Отправляет команду Правка копии. Реализованы в виде:  
  
 `ON_OLECMD(NULL, OLECMDID_COPY, ID_EDIT_COPY)`  
  
 **(ON_OLECMD_CUT)**  
  
 Отправляет команду Изменить Вырезать. Реализованы в виде:  
  
 `ON_OLECMD(NULL, OLECMDID_CUT, ID_EDIT_CUT)`  
  
 **(ON_OLECMD_NEW)**  
  
 Отправляет файл новой команды. Реализованы в виде:  
  
 `ON_OLECMD(NULL, OLECMDID_NEW, ID_FILE_NEW)`  
  
 **(ON_OLECMD_OPEN)**  
  
 Отправляет команды открытия файла. Реализованы в виде:  
  
 `ON_OLECMD(NULL, OLECMDID_OPEN, ID_FILE_OPEN)`  
  
 **(ON_OLECMD_PAGESETUP)**  
  
 Отправляет команду Параметры страницы файла. Реализованы в виде:  
  
 `ON_OLECMD(NULL, OLECMDID_PAGESETUP, ID_FILE_PAGE_SETUP)`  
  
 **(ON_OLECMD_PASTE)**  
  
 Отправляет команду Edit Paste. Реализованы в виде:  
  
 `ON_OLECMD(NULL, OLECMDID_PASTE, ID_EDIT_PASTE)`  
  
 **(ON_OLECMD_PASTESPECIAL)**  
  
 Отправляет команду Специальная вставка. Реализованы в виде:  
  
 `ON_OLECMD(NULL, OLECMDID_PASTESPECIAL, ID_EDIT_PASTE_SPECIAL)`  
  
 **(ON_OLECMD_PRINT)**  
  
 Отправляет команду печати файла. Реализованы в виде:  
  
 `ON_OLECMD(NULL, OLECMDID_PRINT, ID_FILE_PRINT)`  
  
 **(ON_OLECMD_PRINTPREVIEW)**  
  
 Отправляет команду Предварительный просмотр печати файла. Реализованы в виде:  
  
 `ON_OLECMD(NULL, OLECMDID_PRINTPREVIEW, ID_FILE_PRINT_PREVIEW)`  
  
 **(ON_OLECMD_REDO)**  
  
 Отправляет команду Изменить повтора. Реализованы в виде:  
  
 `ON_OLECMD(NULL, OLECMDID_REDO, ID_EDIT_REDO)`  
  
 **(ON_OLECMD_SAVE)**  
  
 Отправляет команду сохранения файла. Реализованы в виде:  
  
 `ON_OLECMD(NULL, OLECMDID_SAVE, ID_FILE_SAVE)`  
  
 **(ON_OLECMD_SAVE_AS)**  
  
 Отправляет команду Сохранить как файл. Реализованы в виде:  
  
 `ON_OLECMD(NULL, OLECMDID_SAVEAS, ID_FILE_SAVE_AS)`  
  
 **(ON_OLECMD_SAVE_COPY_AS)**  
  
 Отправляет файл сохранить копию как команды. Реализованы в виде:  
  
 `ON_OLECMD(NULL, OLECMDID_SAVECOPYAS, ID_FILE_SAVE_COPY_AS)`  
  
 **(ON_OLECMD_SELECTALL)**  
  
 Отправляет команду Изменить выделить все. Реализованы в виде:  
  
 `ON_OLECMD(NULL, OLECMDID_SELECTALL, ID_EDIT_SELECT_ALL)`  
  
 **(ON_OLECMD_UNDO)**  
  
 Отправляет команду Отменить изменение. Реализованы в виде:  
  
 `ON_OLECMD(NULL, OLECMDID_UNDO, ID_EDIT_UNDO)`  
  
### <a name="requirements"></a>Требования  
 **Заголовок:** afxdocob.h  
  
### <a name="see-also"></a>См. также  
 [Класс COleCmdUI](colecmdui-class.md)   
 [COleServerDoc::OnExecOleCmd](coleserverdoc-class.md#onexecolecmd)

## <a name="on_registered_message"></a>ON_REGISTERED_MESSAGE
Windows **RegisterWindowMessage** функция используется для определения новых сообщение окна, которое является гарантированно уникальным во всей системе.  
  
### <a name="syntax"></a>Синтаксис  
  
```  
ON_REGISTERED_MESSAGE( nMessageVariable, memberFxn )  
```  
  
### <a name="parameters"></a>Параметры  
 `nMessageVariable`  
 Переменная ID зарегистрированных сообщения окна.  
  
 `memberFxn`  
 Имя функции обработчика сообщений, с которым сопоставляется сообщение.  
  
### <a name="remarks"></a>Примечания  
 Этот макрос указывает, какую функцию обработки зарегистрированных сообщений.  
  
 Дополнительные сведения и примеры см. в разделе [обработка сообщений и сопоставление разделов](../../mfc/message-handling-and-mapping.md).  
  
### <a name="example"></a>Пример  
```cpp  
static UINT NEAR WM_FIND = RegisterWindowMessage(_T("COMMDLG_FIND"));


BEGIN_MESSAGE_MAP(CMyWnd3, CWnd)
   ON_REGISTERED_MESSAGE(WM_FIND, OnFind)
END_MESSAGE_MAP()
```  
  
### <a name="requirements"></a>Требования  
 **Заголовок:** afxmsg_.h  
  
### <a name="see-also"></a>См. также  
 [RegisterWindowMessage](http://msdn.microsoft.com/library/windows/desktop/ms644947)   
 [Пользовательские обработчики](user-defined-handlers.md)

## <a name="on_registered_thread_message"></a>ON_REGISTERED_THREAD_MESSAGE    
Указывает, какая функция будет обрабатывать сообщения, зарегистрированные с помощью функции Windows RegisterWindowMessage.  
  
### <a name="syntax"></a>Синтаксис  
  
```  
ON_REGISTERED_THREAD_MESSAGE(nMessageVariable, memberFxn )  
```  
  
### <a name="parameters"></a>Параметры  
 `nMessageVariable`  
 Переменная ID зарегистрированных сообщения окна.  
  
 `memberFxn`  
 Имя функции обработчиков сообщений CWinThread, с которым сопоставляется сообщение.  
  
### <a name="remarks"></a>Примечания  
 RegisterWindowMessage используется для определения новых сообщение окна, которое является гарантированно уникальным во всей системе. ON_REGISTERED_THREAD_MESSAGE должен использоваться вместо ON_REGISTERED_MESSAGE при наличии CWinThread-класс. 
  
### <a name="requirements"></a>Требования  
 **Заголовок:** afxmsg_.h  

## <a name="on_thread_message"></a>ON_THREAD_MESSAGE    
Указывает, какая функция будет обрабатывать определенное пользователем сообщение.  
  
### <a name="syntax"></a>Синтаксис  
  
```  
ON_THREAD_MESSAGE( message, memberFxn )  
```  
  
### <a name="parameters"></a>Параметры  
 `message`  
 Идентификатор сообщения.  
  
 `memberFxn`  
 Имя `CWinThread`-сообщение-функция обработчика, с которым сопоставляется сообщение.  
  
### <a name="remarks"></a>Примечания  
 `ON_THREAD_MESSAGE`необходимо использовать вместо `ON_MESSAGE` при наличии `CWinThread` класса. Определяемые пользователем сообщения, все сообщения, которые не являются стандартные **WM_MESSAGE** сообщений. Должно быть ровно один `ON_THREAD_MESSAGE` инструкции макроса в сопоставлении сообщения для каждого определяемого пользователем сообщения должен быть сопоставлен функцию обработки сообщений.  
  
### <a name="requirements"></a>Требования  
 **Заголовок:** afxole.h  

## <a name="on_update_command_ui"></a>ON_UPDATE_COMMAND_UI    
Этот макрос указывает, какая функция будет обрабатывать сообщения команды обновления пользовательского интерфейса.  
  
### <a name="syntax"></a>Синтаксис  
  
```  
ON_UPDATE_COMMAND_UI( id, memberFxn )  
```  
  
### <a name="parameters"></a>Параметры  
 `id`  
 Идентификатор сообщения.  
  
 `memberFxn`  
 Имя функции обработчика сообщений, с которым сопоставляется сообщение.  
  
### <a name="remarks"></a>Примечания  
 Должно быть ровно один `ON_UPDATE_COMMAND_UI` инструкции макроса в сопоставлении сообщения для каждой команды обновления пользовательского интерфейса, должен быть сопоставлен функцию обработки сообщений.  
  
 Дополнительные сведения и примеры см. в разделе [обработка сообщений и сопоставление разделов](../../mfc/message-handling-and-mapping.md).  
  
### <a name="requirements"></a>Требования  
 **Заголовок:** afxole.h  
  
### <a name="see-also"></a>См. также  
 [Класс CCmdUI](ccmdui-class.md)

## <a name="on_command_range"></a>ON_COMMAND_RANGE  
Используйте этот макрос для сопоставления непрерывный диапазон идентификаторов, функция обработчика одно сообщение.  
  
### <a name="syntax"></a>Синтаксис
  
```  
ON_COMMAND_RANGE( id1, id2, memberFxn )  
```  
  
### <a name="parameters"></a>Параметры  
 `id1`  
 Идентификатор команды в начале непрерывный диапазон идентификаторов команд.  
  
 `id2`  
 Идентификатор команды в конце непрерывный диапазон идентификаторов команд.  
  
 `memberFxn`  
 Имя функции обработчика сообщений, с которым сопоставляются команды.  
  
### <a name="remarks"></a>Примечания  
 Диапазон идентификаторов начинается с `id1` и заканчивается `id2`.  
  
 Используйте `ON_COMMAND_RANGE` для сопоставления диапазона идентификаторов команд один член функции. Используйте [ON_COMMAND](#on_command) для сопоставления одной команды к функции-члену. Только одна запись сопоставления сообщений можно сопоставить идентификатор данной команды. То есть не удается сопоставить несколько обработчиков команды. Дополнительные сведения о диапазоны сопоставления сообщений см. [обработчики для диапазонов схем сообщений](../../mfc/handlers-for-message-map-ranges.md).  
  
 Не поддерживается автоматическое для диапазонов схем сообщений, поэтому необходимо поместить макрос самостоятельно.  
  
### <a name="example"></a>Пример  
```cpp  
// The code fragment below shows how to use ON_COMMAND_RANGE macro 
// to map a contiguous range of command IDs to a single message  
// handler function (i.e. OnRangeCmds() in the sample below). In  
// addition, it also shows how to use CheckMenuRadioItem() to check a  
// selected menu item and makes it a radio item.

BEGIN_MESSAGE_MAP(CChildFrame, CMDIChildWnd)
   ON_COMMAND_RANGE(ID_COMMAND_RANGECMD1, ID_COMMAND_RANGECMD3, &CChildFrame::OnRangeCmds)
END_MESSAGE_MAP()

void CChildFrame::OnRangeCmds(UINT nID)
{
   CMenu* mmenu = AfxGetMainWnd()->GetMenu();
   CMenu* submenu = mmenu->GetSubMenu(5);
   submenu->CheckMenuRadioItem(ID_COMMAND_RANGECMD1, ID_COMMAND_RANGECMD3, 
      nID, MF_BYCOMMAND);
}
```
  
### <a name="requirements"></a>Требования  
 **Заголовок:** afxmsg_.h  

## <a name="on_update_command_ui_range"></a>ON_UPDATE_COMMAND_UI_RANGE    
Сопоставляется функции обработки сообщений одно обновление непрерывный диапазон идентификаторов команд.  
  
### <a name="syntax"></a>Синтаксис  
  
```  
ON_UPDATE_COMMAND_UI_RANGE( id1, id2, memberFxn )  
```  
  
### <a name="parameters"></a>Параметры  
 `id1`  
 Идентификатор команды в начале непрерывный диапазон идентификаторов команд.  
  
 `id2`  
 Идентификатор команды в конце непрерывный диапазон идентификаторов команд.  
  
 `memberFxn`  
 Имя функции обработчика сообщений обновления, с которым сопоставляются команды.  
  
### <a name="remarks"></a>Примечания  
 Обработчики сообщений обновление обновления состояния элементов меню и кнопки панели инструментов, связанный с данной командой. Диапазон идентификаторов начинается с `id1` и заканчивается `id2`.  
  
 Не поддерживается автоматическое для диапазонов схем сообщений, поэтому необходимо поместить макрос самостоятельно.  
  
### <a name="requirements"></a>Требования  
 **Заголовок:** afxmsg_.h  

## <a name="on_control_range"></a>ON_CONTROL_RANGE     
Используйте этот макрос для сопоставления непрерывный диапазон идентификаторов элементов управления, функция-обработчик одного сообщения для указанного сообщения уведомления Windows, таких как **BN_CLICKED**.  
  
### <a name="syntax"></a>Синтаксис  
  
```  
ON_CONTROL_RANGE( wNotifyCode, id1, id2, memberFxn )  
```  
  
### <a name="parameters"></a>Параметры  
 `wNotifyCode`  
 Код уведомления, на который отвечает обработчика.  
  
 `id1`  
 Идентификатор команды в начале непрерывный диапазон идентификаторов элементов управления.  
  
 `id2`  
 Идентификатор команды в конце непрерывный диапазон идентификаторов элементов управления.  
  
 `memberFxn`  
 Имя функции обработчика сообщений, с которым сопоставляются элементам управления.  
  
### <a name="remarks"></a>Примечания  
 Диапазон идентификаторов начинается с `id1` и заканчивается `id2`. Обработчик вызывается для заданного уведомления, поступающие от всех сопоставленных элементов управления.  
  
 Не поддерживается автоматическое для диапазонов схем сообщений, поэтому необходимо поместить макрос самостоятельно.  
  
 Дополнительные сведения о реализации функции обработчика для диапазона идентификаторов элементов управления см. [обработчики для диапазонов схем сообщений](../../mfc/handlers-for-message-map-ranges.md).  
  
### <a name="requirements"></a>Требования  
 **Заголовок:** afxmsg_.h  
  



