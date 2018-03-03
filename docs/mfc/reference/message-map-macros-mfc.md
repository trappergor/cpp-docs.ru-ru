---
title: "Макросы схемы (MFC) сообщений | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- AFXWIN/DECLARE_MESSAGE_MAP
- AFXWIN/BEGIN_MESSAGE_MAP
- AFXWIN/BEGIN_TEMPLATE_MESSAGE_MAP
- AFXWIN/END_MESSAGE_MAP
- AFXWIN/ON_COMMAND
- AFXWIN/ON_COMMAND_EX
- AFXWIN/ON_CONTROL
- AFXWIN/ON_MESSAGE
- AFXWIN/ON_OLECMD
- AFXWIN/ON_REGISTERED_MESSAGE
- AFXWIN/ON_REGISTERED_THREAD_MESSAGE
- AFXWIN/ON_THREAD_MESSAGE
- AFXWIN/ON_UPDATE_COMMAND_UI
- AFXWIN/ON_COMMAND_RANGE
- AFXWIN/ON_UPDATE_COMMAND_UI_RANGE
- AFXWIN/ON_CONTROL_RANGE
dev_langs:
- C++
helpviewer_keywords:
- message map macros
- Windows messages [MFC], declaration
- demarcating Windows messages
- message maps [MFC], macros
- message maps [MFC], declaration and demarcation
- message mapping macros
- ranges, message map
- message map ranges
ms.assetid: 531b15ce-32b5-4ca0-a849-bb519616c731
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 7bf56b243118ceb7fdd995fc6970f6c49e0a5499
ms.sourcegitcommit: 54035dce0992ba5dce0323d67f86301f994ff3db
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/03/2018
---
# <a name="message-map-macros-mfc"></a>Макросы схемы сообщений (MFC)
Для поддержки схемы сообщений, MFC предоставляет следующие макросы:  
  
### <a name="message-map-declaration-and-demarcation-macros"></a>Схемы сообщений объявление и определение границ макросы  
  
|||  
|-|-|  
|[DECLARE_MESSAGE_MAP](#declare_message_map)|Объявляет, схему сообщений будет использоваться в классе для сопоставления сообщения с функциями (следует использовать в объявлении класса).|  
|[BEGIN_MESSAGE_MAP](#begin_message_map)|Начинается определение схемы сообщений (следует использовать в реализацию класса).|  
|[BEGIN_TEMPLATE_MESSAGE_MAP](#begin_template_interface_map)|Начинается определение схемы сообщений для типа класса, содержащего аргумента одного шаблона. |
|[END_MESSAGE_MAP](#end_message_map)|Завершает определение схемы сообщений (следует использовать в реализацию класса).|  
  
### <a name="message-mapping-macros"></a>Макросы сопоставления сообщений  
  
|||  
|-|-|  
|[ON_COMMAND](#on_command)|Указывает, какая функция будет обрабатывать сообщения указанную команду.|  
|[ON_COMMAND_EX](#on_command_ex)|Указывает, какая функция будет обрабатывать сообщения указанную команду.|  
|[ON_CONTROL](#on_control)|Указывает, какие функции будет обрабатывать сообщения указанного уведомление элемента управления.|  
|[ON_MESSAGE](#on_message)|Указывает, какие функции будут обрабатывать определенное пользователем сообщение.|  
|[ON_OLECMD](#on_olecmd)|Указывает, какая функция будет обрабатывать команды меню с DocObject или его контейнера.|  
|[ON_REGISTERED_MESSAGE](#on_registered_message)|Указывает, какая функция будет обрабатывать зарегистрированных определенное пользователем сообщение.|  
|[ON_REGISTERED_THREAD_MESSAGE](#on_registered_thread_message)|Указывает, какая функция будет обрабатывать зарегистрированных определяемых пользователем сообщений, при наличии `CWinThread` класса.|  
|[ON_THREAD_MESSAGE](#on_thread_message)|Указывает, какая функция будет обрабатывать определенное пользователем сообщение, при наличии `CWinThread` класса.|  
|[ON_UPDATE_COMMAND_UI](#on_update_command_ui)|Указывает, какая функция будет обрабатывать сообщения команды обновления указанного пользовательского интерфейса.|  
  
### <a name="message-map-range-macros"></a>Макросы схемы сообщений диапазона  
  
|||  
|-|-|  
|[ON_COMMAND_RANGE](#on_command_range)|Указывает, какую функцию обработки диапазона идентификаторов команд, указанный в первые два параметра в макрос.|  
|[ON_UPDATE_COMMAND_UI_RANGE](#on_update_command_ui_range)|Указывает, какой обработчик обновление будет обрабатывать диапазон идентификаторов, указанный в первых двух pa] араметры в макрос.|  
|[ON_CONTROL_RANGE](#on_control_range)|Указывает, какие функции будут обрабатывать уведомления из диапазона идентификаторов, указанных в второй и третий параметры в макрос элемента управления. Первый параметр является сообщением уведомление элемента управления, такие как **BN_CLICKED**.|  
  
 Дополнительные сведения о схемы сообщений, объявление схемы сообщений и определение границ макросы и макросы сопоставления сообщений см. в разделе [схемы сообщений](../../mfc/reference/message-maps-mfc.md) и [обработка сообщений и разделов сопоставления](../../mfc/message-handling-and-mapping.md). Дополнительные сведения о диапазоны схемы сообщений см. в разделе [обработчики для диапазонов схем сообщений](../../mfc/handlers-for-message-map-ranges.md).  


## <a name="begin_message_map"></a>BEGIN_MESSAGE_MAP
Начинается определение схему сообщений.  
  
### <a name="syntax"></a>Синтаксис  
  
```  
BEGIN_MESSAGE_MAP( theClass, baseClass )  
```  
  
### <a name="parameters"></a>Параметры  
 `theClass`  
 Указывает имя класса, сообщение о которой сопоставления.  
  
 `baseClass`  
 Указывает имя базового класса `theClass`.  
  
### <a name="remarks"></a>Примечания  
 В файле реализации (CPP), который определяет функции-члены класса, запустить сопоставление сообщений с `BEGIN_MESSAGE_MAP` макрос, затем добавить макрос записи для каждой из функций обработчиков сообщений и выполните сопоставление сообщений с `END_MESSAGE_MAP` макрос.  
  
 Дополнительные сведения о схемах сообщений см. в разделе [схемы сообщений](message-maps-mfc.md)  
  
### <a name="example"></a>Пример  
```cpp  
BEGIN_MESSAGE_MAP(CMainFrame, CMDIFrameWnd)
   ON_WM_CREATE()
END_MESSAGE_MAP()
```
  
### <a name="requirements"></a>Требования  
 **Заголовок:** afxwin.h 

##  <a name="begin_template_message_map"></a>BEGIN_TEMPLATE_MESSAGE_MAP
Начинается определение схемы сообщений для типа класса, содержащего аргумента одного шаблона.  
   
### <a name="syntax"></a>Синтаксис  
  ```
BEGIN_TEMPLATE_MESSAGE_MAP( theClass, type_name, baseClass )  
```
### <a name="parameters"></a>Параметры  
 `theClass`  
 Указывает имя класса, сообщение о которой сопоставления.    
 `type_name`  
 Имя параметра шаблона, указанный для класса.    
 `baseClass`  
 Указывает имя базового класса `theClass`.  
   
### <a name="remarks"></a>Примечания  
 Этот макрос аналогичен [BEGIN_MESSAGE_MAP](message-map-macros-mfc.md#begin_message_map) макрос; тем не менее, этот макрос предназначен для классов, содержащих аргумента одного шаблона.  
  
 В разделе реализации метода класса, запустить сопоставление сообщений с **BEGIN_TEMPLATE_MESSAGE_MAP** макрос; затем добавить записи макроса для каждого из методов обработчик сообщений, как и для стандартных сообщений карты. Как и в **BEGIN_MESSAGE_MAP** макрос, выполните сопоставление сообщений шаблона с [END_MESSAGE_MAP](message-map-macros-mfc.md#end_message_map) макрос.  
  
 Дополнительные сведения о реализации схемы сообщений для классов шаблонов см. [как: Создание виртуальной схемы сообщений для класса шаблона](../how-to-create-a-message-map-for-a-template-class.md).  
   
### <a name="requirements"></a>Требования  
 **Заголовок:** afxwin.h  
 
## <a name="declare_message_map"></a>DECLARE_MESSAGE_MAP
 Объявляет, что класс определяет схему сообщений. Каждый `CCmdTarget`-производный класс в программе необходимо указать схему сообщений для обработки сообщений.  
  
### <a name="syntax"></a>Синтаксис  
  
```    
DECLARE_MESSAGE_MAP( )  
```  
  
### <a name="remarks"></a>Примечания  
 Используйте `DECLARE_MESSAGE_MAP` макрос в конце объявления класса. В CPP-файле, который определяет функции-члены класса, используйте `BEGIN_MESSAGE_MAP` макрос, макрос записи для каждой из функций обработчик сообщений и `END_MESSAGE_MAP` макрос.  
  
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


## <a name="end_message_map"></a>END_MESSAGE_MAP
Завершает определение схему сообщений.  
  
### <a name="syntax"></a>Синтаксис  
  
```   
END_MESSAGE_MAP( )  
```  
  
### <a name="remarks"></a>Примечания  
 Дополнительные сведения о сообщении сопоставляет и `END_MESSAGE_MAP` макрос, в разделе [обработка сообщений и сопоставление разделов](../../mfc/message-handling-and-mapping.md).  
  
### <a name="requirements"></a>Требования  
 **Заголовок:** afxwin.h  

## <a name="on_command"></a>ON_COMMAND
Этот макрос сообщением команды сопоставляется с функцией-членом.  
  
### <a name="syntax"></a>Синтаксис  
  
```  
ON_COMMAND( id, memberFxn )  
```  
  
### <a name="parameters"></a>Параметры  
 `id`  
 Идентификатор команды.  
  
 `memberFxn`  
 Имя функции обработчик сообщений, с которым сопоставлен команды.  
  
### <a name="remarks"></a>Примечания  
 Он указывает, какие функции будут обрабатывать сообщение команды из объекта команды пользовательского интерфейса, например пункта меню или панели инструментов кнопки.  
  
 Когда целевой объект команды получает Windows **WM_COMMAND** сообщения с указанным Идентификатором `ON_COMMAND` будет вызывать функцию-член `memberFxn` для обработки сообщения.  
  
 Используйте `ON_COMMAND` для сопоставления одной команды с функцией-членом. Используйте [ON_COMMAND_RANGE](#on_command_range) сопоставляемый диапазон идентификаторов, функция один член. Только одна запись схемы сообщений можно сопоставить идентификатор данной команды. То есть команду нельзя сопоставить несколько обработчиков. Дополнительные сведения и примеры см. в разделе [обработка сообщений и сопоставление разделов](../../mfc/message-handling-and-mapping.md).  
  
### <a name="example"></a>Пример  
```cpp  
BEGIN_MESSAGE_MAP(CMFCListViewDoc, CDocument)
   ON_COMMAND(ID_MYCOMMAND, &CMFCListViewDoc::OnMycommand)
END_MESSAGE_MAP()
``` 
  
### <a name="requirements"></a>Требования  
 **Заголовок:** afxmsg_.h  

 ## <a name="on_command_ex"></a>ON_COMMAND_EX
Расширенные функции-члена обработчика команд.  
   
### <a name="syntax"></a>Синтаксис  
  ```  
ON_COMMAND_EX(id, memberFxn);  
```
### <a name="parameters"></a>Параметры  
 `id`  
 Идентификатор команды.  
  
 `memberFxn`  
 Имя функции обработчик сообщений, с которым сопоставлен команды.  
   
### <a name="remarks"></a>Примечания 
Расширенной формы обработчики команд сообщения доступен для расширенного использования. `ON_COMMAND_EX` Макрос используется для таких обработчиков сообщений и предоставляет надмножество функций [ON_COMMAND] (#on_command).  Функции-члены расширенного обработчика команд принимать единственный параметр, **UINT** содержит идентификатор команды и возвращать **BOOL**. Возвращаемое значение должно быть значение TRUE для 

Этот макрос сопоставляет сообщение команды функцию расширенный элемент обработчика команд.  
   
### <a name="syntax"></a>Синтаксис  
```  
ON_COMMAND_EX(id,  memberFxn);  
```
### <a name="parameters"></a>Параметры  
 `id`  
 Идентификатор команды.  
  
 `memberFxn`  
 Имя функции обработчик сообщений, с которым сопоставлен команды.  
   
### <a name="remarks"></a>Примечания  
 Расширенной формы обработчики команд сообщения доступен для расширенного использования. `ON_COMMAND_EX` Макрос используется для таких обработчиков сообщений и предоставляет надмножество [ON_COMMAND](message-map-macros-mfc.md#on_command) функциональные возможности. Функции-члены расширенного обработчика команд принимать единственный параметр, **UINT** содержит идентификатор команды и возвращать **BOOL**. Возвращаемое значение должно быть значение TRUE указывает, что команда было обработано; в противном случае маршрутизации продолжит другие целевые объекты команды.  
Дополнительные сведения см. в разделе техническое Примечание [TN006: схемы сообщений] tm006 сообщения maps.md).  
   
### <a name="requirements"></a>Требования  
 Файл заголовка: afxmsg_.h  
   
### <a name="see-also"></a>См. также  
 [ON_COMMAND](message-map-macros-mfc.md#on_command)   
 [TN006: схемы сообщений] tm006 сообщения maps.md)

  
## <a name="on_control"></a>ON_CONTROL
Указывает, какая функция будет обрабатывать сообщение уведомления пользовательский-элемент управления.  
  
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
 Имя функции обработчик сообщений, с которым сопоставлен команды.  
  
### <a name="remarks"></a>Примечания  
 Уведомляющие сообщения элементов управления являются сообщения от элемента управления своему родительскому окну.  
  
 Должен быть ровно один `ON_CONTROL` макрос инструкции на карте сообщений для каждого сообщения уведомления элемента управления, должен быть сопоставлен с функцией обработчик сообщений.  
  
 Дополнительные сведения и примеры см. в разделе [обработка сообщений и сопоставление разделов](../../mfc/message-handling-and-mapping.md).  
  
### <a name="requirements"></a>Требования  
 **Заголовок:** afxmsg_.h  
  

## <a name="on_message"></a>ON_MESSAGE  
Указывает, какие функции будут обрабатывать определенное пользователем сообщение.  
  
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
 Определяемые пользователем сообщения, все сообщения, которые не являются стандартный Windows `WM_MESSAGE` сообщений. При выборе идентификатор сообщения, необходимо использовать значения в диапазоне от `WM_USER` (0x0400) для 0x7FFF или `WM_APP` (0x8000) для 0xBFFF. Дополнительные сведения о сообщении идентификаторы. в разделе [WM_APP](http://msdn.microsoft.com/library/windows/desktop/ms644930).  
  
 Должен быть ровно один `ON_MESSAGE` макрос инструкции на карте сообщение для каждого определяемого пользователем сообщения должен быть сопоставлен с функцией обработчик сообщений.  
  
> [!NOTE]
>  Помимо определяемых пользователем сообщений `ON_MESSAGE` обрабатывает сообщения Windows, реже. Дополнительные сведения см. статью базы знаний [99848: INFO: используйте макрос ON_MESSAGE() карты менее типичных сообщений](http://go.microsoft.com/fwlink/p/?linkid=192022).  
  
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
Перенаправляет команды через интерфейс диспетчеризации команда `IOleCommandTarget`.  
  
### <a name="syntax"></a>Синтаксис  
  
```  
ON_OLECMD( pguid, olecmdid, id )  
```  
  
### <a name="parameters"></a>Параметры  
 `pguid`  
 Идентификатор группы команд, к которой принадлежит команда. Используйте **NULL** для стандартной группы.  
  
 *olecmdid*  
 Идентификатор команды OLE.  
  
 `id`  
 Идентификатор меню, панели инструментов идентификатор, button ID или другой идентификатор ресурса или объекта команды.  
  
### <a name="remarks"></a>Примечания  
 `IOleCommandTarget`позволяет контейнера для получения команд, создаваемых в DocObject пользовательского интерфейса, а контейнера для отправки команды (такие как New, открыть, сохранить как и печати в меню "файл"; и скопируйте, вставьте и отменить, и так далее, в меню Правка) для DocObject.  
  
 `IOleCommandTarget`проще, чем OLE-автоматизации `IDispatch`. `IOleCommandTarget`полностью зависит от стандартный набор команд, редко иметь аргументы и участвует никакой информации о типе (безопасность типа позволяет уменьшить также аргументы командной строки). Если требуется отправлять команды с аргументами, используйте [COleServerDoc::OnExecOleCmd](coleserverdoc-class.md#onexecolecmd).  
  
 `IOleCommandTarget` Стандартных команд меню с MFC в реализованы следующие макросы:  
  
 **ON_OLECMD_CLEARSELECTION)**  
  
 Отправляет команду Редактировать снимите флажок. Реализован в виде:  
  
 `ON_OLECMD(NULL, OLECMDID_CLEARSELECTION, ID_EDIT_CLEAR)`  
  
 **ON_OLECMD_COPY)**  
  
 Отправляет команду Изменить копирования. Реализован в виде:  
  
 `ON_OLECMD(NULL, OLECMDID_COPY, ID_EDIT_COPY)`  
  
 **ON_OLECMD_CUT)**  
  
 Отправляет команду Изменить Вырезать. Реализован в виде:  
  
 `ON_OLECMD(NULL, OLECMDID_CUT, ID_EDIT_CUT)`  
  
 **ON_OLECMD_NEW)**  
  
 Отправляет команды создания файла. Реализован в виде:  
  
 `ON_OLECMD(NULL, OLECMDID_NEW, ID_FILE_NEW)`  
  
 **ON_OLECMD_OPEN)**  
  
 Отправляет команды открытия файла. Реализован в виде:  
  
 `ON_OLECMD(NULL, OLECMDID_OPEN, ID_FILE_OPEN)`  
  
 **ON_OLECMD_PAGESETUP)**  
  
 Отправляет команду Setup файла страницы. Реализован в виде:  
  
 `ON_OLECMD(NULL, OLECMDID_PAGESETUP, ID_FILE_PAGE_SETUP)`  
  
 **ON_OLECMD_PASTE)**  
  
 Отправляет команду Изменить вставки. Реализован в виде:  
  
 `ON_OLECMD(NULL, OLECMDID_PASTE, ID_EDIT_PASTE)`  
  
 **ON_OLECMD_PASTESPECIAL)**  
  
 Отправляет команду Специальная вставка. Реализован в виде:  
  
 `ON_OLECMD(NULL, OLECMDID_PASTESPECIAL, ID_EDIT_PASTE_SPECIAL)`  
  
 **ON_OLECMD_PRINT)**  
  
 Отправляет команды Печать файла. Реализован в виде:  
  
 `ON_OLECMD(NULL, OLECMDID_PRINT, ID_FILE_PRINT)`  
  
 **ON_OLECMD_PRINTPREVIEW)**  
  
 Отправляет команду предварительного просмотра перед печатью файла. Реализован в виде:  
  
 `ON_OLECMD(NULL, OLECMDID_PRINTPREVIEW, ID_FILE_PRINT_PREVIEW)`  
  
 **ON_OLECMD_REDO)**  
  
 Отправляет команду Изменить повтора. Реализован в виде:  
  
 `ON_OLECMD(NULL, OLECMDID_REDO, ID_EDIT_REDO)`  
  
 **ON_OLECMD_SAVE)**  
  
 Отправляет команду сохранения файла. Реализован в виде:  
  
 `ON_OLECMD(NULL, OLECMDID_SAVE, ID_FILE_SAVE)`  
  
 **ON_OLECMD_SAVE_AS)**  
  
 Отправляет команду Сохранить как файл. Реализован в виде:  
  
 `ON_OLECMD(NULL, OLECMDID_SAVEAS, ID_FILE_SAVE_AS)`  
  
 **ON_OLECMD_SAVE_COPY_AS)**  
  
 Отправляет файл сохранить копию как команду. Реализован в виде:  
  
 `ON_OLECMD(NULL, OLECMDID_SAVECOPYAS, ID_FILE_SAVE_COPY_AS)`  
  
 **ON_OLECMD_SELECTALL)**  
  
 Отправляет команду Изменить выделить все. Реализован в виде:  
  
 `ON_OLECMD(NULL, OLECMDID_SELECTALL, ID_EDIT_SELECT_ALL)`  
  
 **ON_OLECMD_UNDO)**  
  
 Отправляет команду Отменить изменение. Реализован в виде:  
  
 `ON_OLECMD(NULL, OLECMDID_UNDO, ID_EDIT_UNDO)`  
  
### <a name="requirements"></a>Требования  
 **Заголовок:** afxdocob.h  
  
### <a name="see-also"></a>См. также  
 [Класс COleCmdUI](colecmdui-class.md)   
 [COleServerDoc::OnExecOleCmd](coleserverdoc-class.md#onexecolecmd)

## <a name="on_registered_message"></a>ON_REGISTERED_MESSAGE
Windows **RegisterWindowMessage** функция используется для определения нового сообщение окна, которое гарантированно будет уникальным во всей системе.  
  
### <a name="syntax"></a>Синтаксис  
  
```  
ON_REGISTERED_MESSAGE( nMessageVariable, memberFxn )  
```  
  
### <a name="parameters"></a>Параметры  
 `nMessageVariable`  
 Переменная идентификатор зарегистрированного сообщения окна.  
  
 `memberFxn`  
 Имя функции обработчика сообщений, с которым сопоставляется сообщение.  
  
### <a name="remarks"></a>Примечания  
 Этот макрос указывает, какие функции будут обрабатывать зарегистрированных сообщения.  
  
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
 Переменная идентификатор зарегистрированного сообщения окна.  
  
 `memberFxn`  
 Имя функции обработчика сообщений CWinThread, с которым сопоставляется сообщение.  
  
### <a name="remarks"></a>Примечания  
 RegisterWindowMessage используется для определения нового сообщение окна, которое гарантированно будет уникальным во всей системе. ON_REGISTERED_THREAD_MESSAGE должен использоваться вместо ON_REGISTERED_MESSAGE при наличии CWinThread-класс. 
  
### <a name="requirements"></a>Требования  
 **Заголовок:** afxmsg_.h  

## <a name="on_thread_message"></a>ON_THREAD_MESSAGE  
Указывает, какие функции будут обрабатывать определенное пользователем сообщение.  
  
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
 `ON_THREAD_MESSAGE`должен использоваться вместо `ON_MESSAGE` при наличии `CWinThread` класса. Определяемые пользователем сообщения, все сообщения, которые не являются стандартный Windows **WM_MESSAGE** сообщений. Должен быть ровно один `ON_THREAD_MESSAGE` макрос инструкции на карте сообщение для каждого определяемого пользователем сообщения должен быть сопоставлен с функцией обработчик сообщений.  
  
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
 Должен быть ровно один `ON_UPDATE_COMMAND_UI` макрос инструкции на карте сообщения для каждой команды обновления пользовательского интерфейса, который должен быть сопоставлен с функцией обработчик сообщений.  
  
 Дополнительные сведения и примеры см. в разделе [обработка сообщений и сопоставление разделов](../../mfc/message-handling-and-mapping.md).  
  
### <a name="requirements"></a>Требования  
 **Заголовок:** afxole.h  
  
### <a name="see-also"></a>См. также  
 [Класс CCmdUI](ccmdui-class.md)

## <a name="on_command_range"></a>ON_COMMAND_RANGE  
Используйте этот макрос для сопоставления непрерывный диапазон идентификаторов, функция обработки одного сообщения.  
  
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
 Имя функции обработчика сообщений, с которыми связаны команды.  
  
### <a name="remarks"></a>Примечания  
 Диапазон идентификаторов начинается с `id1` и заканчивается `id2`.  
  
 Используйте `ON_COMMAND_RANGE` сопоставляемый диапазон идентификаторов, функция один член. Используйте [ON_COMMAND](#on_command) для сопоставления одной команды с функцией-членом. Только одна запись схемы сообщений можно сопоставить идентификатор данной команды. То есть команду нельзя сопоставить несколько обработчиков. Дополнительные сведения о сопоставлении диапазоны сообщений см. в разделе [обработчики для диапазонов схем сообщений](../../mfc/handlers-for-message-map-ranges.md).  
  
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
Сопоставляет непрерывный диапазон идентификаторов, функция-обработчик сообщений одно обновление.  
  
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
 Имя функции обработчика сообщений обновления, с которыми связаны команды.  
  
### <a name="remarks"></a>Примечания  
 Обработчики сообщений обновления обновить состояние элементов меню и кнопки панели инструментов, связанный с данной командой. Диапазон идентификаторов начинается с `id1` и заканчивается `id2`.  
  
 Не поддерживается автоматическое для диапазонов схем сообщений, поэтому необходимо поместить макрос самостоятельно.  
  
### <a name="requirements"></a>Требования  
 **Заголовок:** afxmsg_.h  

## <a name="on_control_range"></a>ON_CONTROL_RANGE     
Используйте этот макрос для сопоставления непрерывный диапазон идентификаторов элементов управления, функция-обработчик одно сообщение для указанного сообщения уведомлений Windows, таких как **BN_CLICKED**.  
  
### <a name="syntax"></a>Синтаксис  
  
```  
ON_CONTROL_RANGE( wNotifyCode, id1, id2, memberFxn )  
```  
  
### <a name="parameters"></a>Параметры  
 `wNotifyCode`  
 Код уведомления, к которому отвечает обработчиком.  
  
 `id1`  
 Идентификатор команды в начале непрерывный диапазон идентификаторов элементов управления.  
  
 `id2`  
 Идентификатор команды в конце непрерывный диапазон идентификаторов элементов управления.  
  
 `memberFxn`  
 Имя функции обработчик сообщений, с которой сопоставляются элементы управления.  
  
### <a name="remarks"></a>Примечания  
 Диапазон идентификаторов начинается с `id1` и заканчивается `id2`. Обработчик вызывается для указанного уведомлений, поступающих от всех сопоставленном элементов управления.  
  
 Не поддерживается автоматическое для диапазонов схем сообщений, поэтому необходимо поместить макрос самостоятельно.  
  
 Дополнительные сведения о реализации функции обработчика для диапазона идентификаторов элементов управления см. [обработчики для диапазонов схем сообщений](../../mfc/handlers-for-message-map-ranges.md).  
  
### <a name="requirements"></a>Требования  
 **Заголовок:** afxmsg_.h  
  


