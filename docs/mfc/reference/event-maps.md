---
title: "Схемы событий | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vc.mfc.macros.maps
dev_langs:
- C++
helpviewer_keywords:
- event maps
ms.assetid: 1ed53aee-bc53-43cd-834a-6fb935c0d29b
caps.latest.revision: 15
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
ms.sourcegitcommit: 17a158366f94d27b7a46917282425d652e6b9042
ms.openlocfilehash: 4c4777496ce609d7c2fa20da726f211264095b6e
ms.lasthandoff: 02/24/2017

---
# <a name="event-maps"></a>Схемы событий
Всякий раз, когда элемент управления, которые будут уведомлять его контейнера, что произошло какое-либо действие (определяется разработчиком элемента управления), (например, нажатие клавиши, щелчок мыши или изменение состояния элемента управления), он вызывает функцию запуска событий. Эта функция уведомляет о произошедшем некоторые важные действия, связанные события контейнера элемента управления.  
  
 Библиотеки классов Microsoft Foundation предоставляет модель программирования, оптимизированный для инициирования событий. В этой модели «схемы событий» позволяют указать, какие функции срабатывают какие события для конкретного элемента управления. Схемы событий содержат один макрос для каждого события. Например схема событий, запускают stock щелкните событие может выглядеть следующим образом:  
  
 [!code-cpp[NVC_MFCAxCtl №&16;](../../mfc/reference/codesnippet/cpp/event-maps_1.cpp)]  
  
 **EVENT_STOCK_CLICK** макрос указывает, что элемент управления будет срабатывать stock выберите событие каждый раз при обнаружении мышь, нажмите кнопку. Более подробное описание других стандартных событий, см. в статье [элементы управления ActiveX: события](../../mfc/mfc-activex-controls-events.md). Макросы используются также для указания пользовательских событий.  
  
 Несмотря на то, что макросы схемы событий являются важными, обычно не будет вставлена их напрямую. Это вызвано окно свойств автоматически создает записи карты событий в исходные файлы при использовании связывание функции обработки событий с событиями. Каждый раз, когда нужно изменить или добавить запись событий карты, можно использовать окно свойств.  
  
 Для поддержки схемы событий, MFC предоставляет следующие макросы:  
  
### <a name="event-map-declaration-and-demarcation"></a>Объявление события карты и определение границ  
  
|||  
|-|-|  
|[DECLARE_EVENT_MAP](#declare_event_map)|Объявляет, что схема событий будет использоваться в классе для сопоставления событий для события Click функции (необходимо использовать в объявлении класса).|  
|[BEGIN_EVENT_MAP](#begin_event_map)|Начинается определение картой событий (необходимо использовать реализацию класса).|  
|[END_EVENT_MAP](#end_event_map)|Завершает определение картой событий (необходимо использовать реализацию класса).|  
  
### <a name="event-mapping-macros"></a>Макросы сопоставления событий  
  
|||  
|-|-|  
|[EVENT_CUSTOM](#event_custom)|Указывает, какую функцию запуска событий будут срабатывать указанного события.|  
|[EVENT_CUSTOM_ID](#event_custom_id)|Указывает, какую функцию запуска событий будут срабатывать указанное событие с идентификатором назначенного диспетчеризации.|  
  
### <a name="message-mapping-macros"></a>Макросы сопоставления сообщений  
  
|||  
|-|-|  
|[ON_OLEVERB](#on_oleverb)|Указывает пользовательских команд, обрабатываются элементом управления OLE.|  
|[ON_STDOLEVERB](#on_stdoleverb)|Переопределяет сопоставление стандартные команды управления OLE.|  
  
##  <a name="a-namedeclareeventmapa--declareeventmap"></a><a name="declare_event_map"></a>DECLARE_EVENT_MAP  
 Каждый `COleControl`-производный класс в программе может предоставлять картой событий для указания событий, элемент управления будет срабатывать.  
  
```   
DECLARE_EVENT_MAP()   
```  
  
### <a name="remarks"></a>Примечания  
 Используйте `DECLARE_EVENT_MAP` макрос в конце объявления класса. В CPP-файле, который определяет функции-члены класса, используйте `BEGIN_EVENT_MAP` макрос, макрос операции для каждого из событий элемента управления и `END_EVENT_MAP` макрос для объявления в конец списка событий.  
  
 Дополнительные сведения о картах событий см. в статье [элементы управления ActiveX: события](../../mfc/mfc-activex-controls-events.md).  
  
### <a name="requirements"></a>Требования  
  **Заголовок** afxctl.h  
  
##  <a name="a-namebegineventmapa--begineventmap"></a><a name="begin_event_map"></a>BEGIN_EVENT_MAP  
 Начинается определение карты событий.  
  
```   
BEGIN_EVENT_MAP(theClass,  baseClass)  
```  
  
### <a name="parameters"></a>Параметры  
 `theClass`  
 Указывает, что имя класса элемента управления, событие которого сопоставления.  
  
 `baseClass`  
 Указывает имя базового класса `theClass`.  
  
### <a name="remarks"></a>Примечания  
 В файле реализации (CPP), который определяет функции-члены класса, запустить сопоставление событий с `BEGIN_EVENT_MAP` макрос, затем добавить макрос записи для каждого события и выполнить сопоставление событий с `END_EVENT_MAP` макрос.  
  
 Дополнительные сведения о событии сопоставляет и `BEGIN_EVENT_MAP` макрос, см. в статье [элементы управления ActiveX: события](../../mfc/mfc-activex-controls-events.md).  
  
### <a name="requirements"></a>Требования  
  **Заголовок** afxctl.h  
  
##  <a name="a-nameendeventmapa--endeventmap"></a><a name="end_event_map"></a>END_EVENT_MAP  
 Используйте `END_EVENT_MAP` макрос для завершения определения события карты.  
  
```   
END_EVENT_MAP()   
```  
  
### <a name="requirements"></a>Требования  
  **Заголовок** afxctl.h  
  
##  <a name="a-nameeventcustoma--eventcustom"></a><a name="event_custom"></a>EVENT_CUSTOM  
 Определяет запись событий карты для пользовательских событий.  
  
```   
EVENT_CUSTOM(pszName, pfnFire,  vtsParams) 
```  
  
### <a name="parameters"></a>Параметры  
 `pszName`  
 Имя события.  
  
 `pfnFire`  
 Имя события функции.  
  
 `vtsParams`  
 Разделенный пробелами список из одной или нескольких констант, указав список параметров функции.  
  
### <a name="remarks"></a>Примечания  
 `vtsParams` Параметр является разделенный пробелами список значений из **VTS_** константы. Один или несколько из этих значений, разделенных пробелами (не запятые) Указывает список параметров функции. Пример:  
  
 [!code-cpp[NVC_MFCActiveXControl&#13;](../../mfc/codesnippet/cpp/event-maps_2.cpp)]  
  
 Указывает список, содержащий 32-разрядное целое число, представляющее RGB цвета значение, следуют указатель **IFontDisp** интерфейс OLE-объекта шрифта.  
  
 **VTS_** константы имеют следующим образом:  
  
|Символ|Тип параметра|  
|------------|--------------------|  
|**VTS_I2**|**short**|  
|**VTS_I4**|**long**|  
|**VTS_R4**|**float**|  
|**VTS_R8**|**double**|  
|**VTS_COLOR**|**OLE_COLOR**|  
|**VTS_CY**|**ВАЛЮТА**|  
|**VTS_DATE**|**ДАТА**|  
|**VTS_BSTR**|**const char\***|  
|**VTS_DISPATCH**|`LPDISPATCH`|  
|**VTS_FONT**|**IFontDispatch\***|  
|**VTS_HANDLE**|`HANDLE`|  
|**VTS_SCODE**|`SCODE`|  
|**VTS_BOOL**|**BOOL**|  
|**VTS_VARIANT**|**const VARIANT\***|  
|**VTS_PVARIANT**|**VARIANT\***|  
|**VTS_UNKNOWN**|`LPUNKNOWN`|  
|**VTS_OPTEXCLUSIVE**|**OLE_OPTEXCLUSIVE**|  
|**VTS_PICTURE**|**IPictureDisp\***|  
|**VTS_TRISTATE**|**OLE_TRISTATE**|  
|**VTS_XPOS_PIXELS**|**OLE_XPOS_PIXELS**|  
|**VTS_YPOS_PIXELS**|**OLE_YPOS_PIXELS**|  
|**VTS_XSIZE_PIXELS**|**OLE_XSIZE_PIXELS**|  
|**VTS_YSIZE_PIXELS**|**OLE_YSIZE_PIXELS**|  
|**VTS_XPOS_HIMETRIC**|**OLE_XPOS_HIMETRIC**|  
|**VTS_YPOS_HIMETRIC**|**OLE_YPOS_HIMETRIC**|  
|**VTS_XSIZE_HIMETRIC**|**OLE_XSIZE_HIMETRIC**|  
|**VTS_YSIZE_HIMETRIC**|**OLE_YSIZE_HIMETRIC**|  
  
> [!NOTE]
>  Дополнительные variant константы определены для всех типов variant, за исключением класса **VTS_FONT** и **VTS_PICTURE**, обеспечивающие указатель константы данных variant. Эти константы именуются **VTS_P** `constantname` соглашение. Например **VTS_PCOLOR** — это указатель на **VTS_COLOR** константой.  
  
### <a name="requirements"></a>Требования  
  **Заголовок** afxctl.h  
  
##  <a name="a-nameeventcustomida--eventcustomid"></a><a name="event_custom_id"></a>EVENT_CUSTOM_ID  
 Определяет события для пользовательского события, относящегося к диспетчеризации Идентификатором, указанным параметром функцию `dispid`.  
  
```   
EVENT_CUSTOM_ID(
  pszName,   
  dispid,   
  pfnFire,
  vtsParams)  
 
```  
  
### <a name="parameters"></a>Параметры  
 `pszName`  
 Имя события.  
  
 `dispid`  
 Идентификатор диспетчеризации, используемые элементом управления при порождении события.  
  
 `pfnFire`  
 Имя события функции.  
  
 `vtsParams`  
 Список параметров переменной передается контейнера элемента управления, когда событие.  
  
### <a name="remarks"></a>Примечания  
 `vtsParams` Аргумент является разделенный пробелами список значений из **VTS_** константы. Один или несколько из этих значений, разделенных пробелами, запятыми, указывает список параметров функции. Пример:  
  
 [!code-cpp[NVC_MFCActiveXControl&#13;](../../mfc/codesnippet/cpp/event-maps_2.cpp)]  
  
 Указывает список, содержащий 32-разрядное целое число, представляющее RGB цвета значение, следуют указатель **IFontDisp** интерфейс OLE-объекта шрифта.  
  
 Список **VTS_** константы, в разделе [EVENT_CUSTOM](#event_custom).  
  
### <a name="requirements"></a>Требования  
  **Заголовок** afxctl.h  
  
##  <a name="a-nameonoleverba--onoleverb"></a><a name="on_oleverb"></a>ON_OLEVERB  
 Этот макрос определяет запись карты сообщения, которая сопоставляет пользовательских команд для функции-члена конкретного элемента управления.  
  
```   
ON_OLEVERB(idsVerbName,  memberFxn)   
```  
  
### <a name="parameters"></a>Параметры  
 *idsVerbName*  
 Идентификатор строкового ресурса имени команды.  
  
 `memberFxn`  
 Функция вызывается инфраструктурой при вызове команды.  
  
### <a name="remarks"></a>Примечания  
 Редактор ресурсов может использоваться для создания имен пользовательских команд, которые добавляются в таблицу строки.  
  
 Прототип функции для `memberFxn` является:  
  
 `BOOL memberFxn(`    
 `LPMSG` `lpMsg` `,`   
 `HWND` `hWndParent` `,`   
 `LPCRECT` `lpRect`   `);`  
  
 Значения `lpMsg`, `hWndParent`, и `lpRect` параметры берутся из соответствующих параметров **функция IOleObject::DoVerb** функции-члена.  
  
### <a name="requirements"></a>Требования  
  **Заголовок** afxole.h  
  
##  <a name="a-nameonstdoleverba--onstdoleverb"></a><a name="on_stdoleverb"></a>ON_STDOLEVERB  
 Используйте этот макрос для переопределения поведения по умолчанию используется стандартная команда.  
  
```   
ON_STDOLEVERB(iVerb,   memberFxn)   
```  
  
### <a name="parameters"></a>Параметры  
 `iVerb`  
 Индекс стандартные команды для переопределения команды.  
  
 `memberFxn`  
 Функция вызывается инфраструктурой при вызове команды.  
  
### <a name="remarks"></a>Примечания  
 Индекс стандартная команда имеет вид **OLEIVERB_**, а затем действие. `OLEIVERB_SHOW`, `OLEIVERB_HIDE`, и `OLEIVERB_UIACTIVATE` приведены примеры стандартных команд.  
  
 В разделе [ON_OLEVERB](#on_oleverb) описание прототип функции для использования в качестве `memberFxn` параметр.  

  
### <a name="requirements"></a>Требования  
  **Заголовок** afxole.h  
    
## <a name="see-also"></a>См. также  
 [Макросы и глобальные объекты](../../mfc/reference/mfc-macros-and-globals.md)

