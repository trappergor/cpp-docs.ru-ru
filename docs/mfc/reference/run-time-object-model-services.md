---
title: Службы модели объекта во время выполнения | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- vc.mfc.macros
dev_langs:
- C++
helpviewer_keywords:
- run-time object model services macros
ms.assetid: 4a3e79df-2ee3-43a4-8193-20298828de85
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: cff506d559ab44ba4034e982bb909db763917594
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="run-time-object-model-services"></a>Службы модели объекта во время выполнения
Классы [CObject](../../mfc/reference/cobject-class.md) и [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) инкапсуляции нескольких объектов служб, включая доступ к сведениям о классе во время выполнения, сериализации и динамическое создание объектов. Все классы, производные от `CObject` наследуют эти функциональные возможности.  
  
 Доступ к сведениям о классе во время выполнения позволяет определить сведения о классе объекта во время выполнения. Возможность определения класса объекта во время выполнения полезно в тех случаях, когда требуется дополнительное проверку типов аргументов функции, и когда необходимо написать код специального назначения, на основе класса объекта. Сведения о классе во время выполнения не поддерживается языком C++.  
  
 Сериализация — это процесс записи или при чтении содержимого объекта в или из файла. Можно использовать сериализацию для хранения содержимого этого объекта, даже после завершения работы приложения. Объект может считываться из файла при перезапуске приложения. Такие объекты данных, называются «постоянный».  
  
 Динамическое создание объектов позволяет создать объект класса, указанного во время выполнения. Например документов, представления и объекты кадра должен поддерживать динамическое создание так, как платформа необходимо динамическое создание.  
  
 В следующей таблице перечислены макросов MFC, которые поддерживают сведения о классе во время выполнения, сериализации и динамическое создание.  
  
 Дополнительные сведения об этих объектов среды выполнения служб и сериализации см. в статье [класс CObject: доступ к сведениям о классе во время выполнения](../../mfc/accessing-run-time-class-information.md).  
  
### <a name="run-time-object-model-services-macros"></a>Макросы служб времени выполнения объектной модели  
  


|||  
|-|-|  
|[DECLARE_DYNAMIC](#declare_dynamic)|Обеспечивает доступ к информации класса среды выполнения (следует использовать в объявлении класса).|  
|[DECLARE_DYNCREATE](#declare_dyncreate)|Обеспечивает динамическое создание и доступ к сведениям о классе во время выполнения (следует использовать в объявлении класса).|  
|[DECLARE_SERIAL](#declare_serial)|Позволяет выполнять сериализацию и доступ к сведениям о классе во время выполнения (следует использовать в объявлении класса).|  
|[IMPLEMENT_DYNAMIC](#implement_dynamic)|Обеспечивает доступ к информации класса среды выполнения (следует использовать в реализацию класса).|  
|[IMPLEMENT_DYNCREATE](#implement_dyncreate)|Обеспечивает динамическое создание и доступ к данным во время выполнения (следует использовать в реализацию класса).|  
|[IMPLEMENT_SERIAL](#implement_serial)|Позволяет выполнять сериализацию и доступ к сведениям о классе во время выполнения (следует использовать в реализацию класса).|  
|[RUNTIME_CLASS](#runtime_class)|Возвращает `CRuntimeClass` структуры, относящейся к именованному классу.|  


 OLE часто требуется динамическое создание объектов во время выполнения. Например приложения сервера OLE необходима для создания OLE-элементы динамически в ответ на запрос от клиента. Аналогичным образом сервер автоматизации необходима возможность создавать элементы в ответ на запросы от клиентов автоматизации.  
  
 Библиотеки классов Microsoft Foundation предоставляет два макроса конкретных OLE.  
  
### <a name="dynamic-creation-of-ole-objects"></a>Динамическое создание объектов OLE  

 






|||  
|-|-|  
|[AFX_COMCTL32_IF_EXISTS](#afx_comctl32_if_exists)|Определяет, реализует ли общие элементы управления библиотеки указанного API.|
|[AFX_COMCTL32_IF_EXISTS2](#afx_comctl32_if_exists2)|Определяет, реализует ли общие элементы управления библиотеки указанного API.|
|[DECLARE_OLECREATE](#declare_olecreate)|Позволяет объектам для создания с помощью OLE-автоматизации.|  
|[DECLARE_OLECTLTYPE](#declare_olectltype)|Объявляет **GetUserTypeNameID** и `GetMiscStatus` функции-члены класса элемента управления.|
|[DECLARE_PROPPAGEIDS](#declare_proppageids)|Объявляет, что элемент управления OLE предоставляет список страницы свойств, чтобы отобразить ее свойства.|
|[IMPLEMENT_OLECREATE](#implement_olecreate)|Позволяет объектам, создаваемых системой OLE.|  
|[IMPLEMENT_OLECTLTYPE](#implement_olectltype)|Реализует **GetUserTypeNameID** и `GetMiscStatus` функции-члены класса элемента управления.|  
|[IMPLEMENT_OLECREATE_FLAGS](#implement_olecreate_flags)|Либо этот макрос или [IMPLEMENT_OLECREATE](#implement_olecreate) должен быть указан в файле реализации для любого класса, который использует `DECLARE_OLECREATE`. |

## <a name="afx_comctl32_if_exists"></a> AFX_COMCTL32_IF_EXISTS
Определяет, реализует ли общие элементы управления библиотеки указанного API.  
   
### <a name="syntax"></a>Синтаксис  
  ```  
AFX_COMCTL32_IF_EXISTS(  proc );  
```
### <a name="parameters"></a>Параметры  
 `proc`  
 Указатель на символом null строку, содержащую имя функции или указывает порядковое значение функции. Если этот параметр имеет порядковый номер, он должен быть в младшее слово; старшее слово должно быть нулевым. Этот параметр должен быть в формате Юникод.  
   
### <a name="remarks"></a>Примечания  
 Используйте этот макрос для определения, является ли общие элементы управления библиотеки функция заданный `proc` (вместо вызова метода [GetProcAddress](http://msdn.microsoft.com/library/windows/desktop/ms683212).  
   
### <a name="requirements"></a>Требования  
 afxcomctl32.h, afxcomctl32.inl  
   
### <a name="see-also"></a>См. также  
 [Изоляция MFC Общие элементы управления библиотеки](../isolation-of-the-mfc-common-controls-library.md) [AFX_COMCTL32_IF_EXISTS2](#afx_comctl32_if_exists2)
 
## <a name="afx_comctl32_if_exists2"></a>  AFX_COMCTL32_IF_EXISTS2
Определяет, реализует ли общие элементы управления библиотеки указанный API (это версия Юникода [AFX_COMCTL32_IF_EXISTS](#afx_comctl32_if_exists)).  
   
### <a name="syntax"></a>Синтаксис    
```  
AFX_COMCTL32_IF_EXISTS2( proc );  
```
### <a name="parameters"></a>Параметры  
 `proc`  
 Указатель на символом null строку, содержащую имя функции или указывает порядковое значение функции. Если этот параметр имеет порядковый номер, он должен быть в младшее слово; старшее слово должно быть нулевым. Этот параметр должен быть в формате Юникод.  
   
### <a name="remarks"></a>Примечания  
 Используйте этот макрос для определения, является ли общие элементы управления библиотеки функция заданный `proc` (вместо вызова метода [GetProcAddress](http://msdn.microsoft.com/library/windows/desktop/ms683212). Этот макрос имеет версию Юникода для `AFX_COMCTL32_IF_EXISTS`.  
   
### <a name="requirements"></a>Требования  
 afxcomctl32.h, afxcomctl32.inl  
   
### <a name="see-also"></a>См. также  
 [Изоляция MFC Общие элементы управления библиотеки](../isolation-of-the-mfc-common-controls-library.md) [AFX_COMCTL32_IF_EXISTS](#afx_comctl32_if_exists)



##  <a name="declare_dynamic"></a>  DECLARE_DYNAMIC  
 Добавляет возможность доступа к среде выполнения сведения о классе объекта при наследовании от класса `CObject`.  
  
```
DECLARE_DYNAMIC(class_name) 
```  
  
### <a name="parameters"></a>Параметры  
 *class_name*  
 Фактическое имя класса.  
  
### <a name="remarks"></a>Примечания  
 Добавить `DECLARE_DYNAMIC` макрос в модуль заголовка (.h) для класса, включите этот модуль во всех модулях .cpp, которым необходим доступ к объектам этого класса.  
  
 При использовании **DECLARE**_ **динамическое** и `IMPLEMENT_DYNAMIC` макросов, как описано, можно использовать `RUNTIME_CLASS` макрос и `CObject::IsKindOf` функцию, чтобы определить класс объектов при запуске время.  
  
 Если `DECLARE_DYNAMIC` включен в объявление класса, а затем `IMPLEMENT_DYNAMIC` должны быть включены в реализацию класса.  
  
 Дополнительные сведения о `DECLARE_DYNAMIC` макрос, в разделе [разделы класс CObject](../../mfc/using-cobject.md).  
  
### <a name="example"></a>Пример  
 Далее приведен пример [IMPLEMENT_DYNAMIC](#implement_dynamic).  

### <a name="requirements"></a>Требования  
 **Заголовок:** afx.h 

##  <a name="declare_dyncreate"></a>  DECLARE_DYNCREATE  
 Включает объекты `CObject`-производные классы создаваться динамически во время выполнения.  
  
```
DECLARE_DYNCREATE(class_name)   
```  
  
### <a name="parameters"></a>Параметры  
 *class_name*  
 Фактическое имя класса.  
  
### <a name="remarks"></a>Примечания  
 Платформа использует эту возможность для динамического создания новых объектов. Например новое представление создается при открытии документа. Кадр классы документов, представления и должен поддерживать динамическое создание, так как платформа необходимо динамическое создание.  
  
 Добавить `DECLARE_DYNCREATE` макрос в модуле .h для класса, включите этот модуль во всех модулях .cpp, которым необходим доступ к объектам этого класса.  
  
 Если `DECLARE_DYNCREATE` включен в объявление класса, а затем `IMPLEMENT_DYNCREATE` должны быть включены в реализацию класса.  
  
 Дополнительные сведения о `DECLARE_DYNCREATE` макрос, в разделе [разделы класс CObject](../../mfc/using-cobject.md).  
  
> [!NOTE]
>  `DECLARE_DYNCREATE` Макрос включает все функциональные возможности `DECLARE_DYNAMIC`.  
  
### <a name="example"></a>Пример  
 Далее приведен пример [IMPLEMENT_DYNCREATE](#implement_dyncreate).  

### <a name="requirements"></a>Требования  
 **Заголовок:** afx.h 

 
## <a name="declareolectltype"></a>DECLARE_OLECTLTYPE
Объявляет **GetUserTypeNameID** и `GetMiscStatus` функции-члены класса элемента управления.  
   
### <a name="syntax"></a>Синтаксис    
```
DECLARE_OLECTLTYPE( class_name )  
```
### <a name="parameters"></a>Параметры  
 *class_name*  
 Имя класса элемента управления.  
   
### <a name="remarks"></a>Примечания  
 **GetUserTypeNameID** и `GetMiscStatus` являются чистые виртуальные функции, объявленные в `COleControl`. Поскольку эти функции являются чисто виртуальные, они должны быть переопределены в классе элемента управления. В дополнение к **DECLARE_OLECTLTYPE**, необходимо добавить `IMPLEMENT_OLECTLTYPE` макрос к объявлению класса элемента управления.  
   
### <a name="requirements"></a>Требования  
 **Заголовок:** afxctl.h  
   
### <a name="see-also"></a>См. также  
 [IMPLEMENT_OLECTLTYPE](#implement_olectltype)
 

## <a name="declareproppageids"></a>DECLARE_PROPPAGEIDS
Объявляет, что элемент управления OLE предоставляет список страницы свойств, чтобы отобразить ее свойства.  
   
### <a name="syntax"></a>Синтаксис    
```
DECLARE_PROPPAGEIDS( class_name )  
```
### <a name="parameters"></a>Параметры  
 *class_name*  
 Имя класса элемента управления, которому принадлежит страницы свойств.  
   
### <a name="remarks"></a>Примечания  
 Используйте `DECLARE_PROPPAGEIDS` макрос в конце объявления класса. В CPP-файле, который определяет функции-члены класса, используйте `BEGIN_PROPPAGEIDS` макрос, макрос записи для каждой из страниц свойств элемента управления и `END_PROPPAGEIDS` макрос для объявления в конец списка страницы свойств.  
  
 Дополнительные сведения о страницах свойств см. в статье [элементы управления ActiveX: страницы свойств](../mfc-activex-controls-property-pages.md).  
   
### <a name="requirements"></a>Требования  
 **Заголовок:** afxctl.h  
   
### <a name="see-also"></a>См. также   
 [BEGIN_PROPPAGEIDS](#begin_proppageids)   
 [END_PROPPAGEIDS](#end_proppageids)

##  <a name="declare_serial"></a>  DECLARE_SERIAL  
 Создает заголовок код C++, необходимые для `CObject`-производного класса, который может быть сериализован.  
  
```
DECLARE_SERIAL(class_name)   
```  
  
### <a name="parameters"></a>Параметры  
 *class_name*  
 Фактическое имя класса.  
  
### <a name="remarks"></a>Примечания  
 Сериализация — это процесс записи или при чтении содержимого объекта к и из файла.  
  
 Используйте `DECLARE_SERIAL` макрос в модуле .h, а затем включить этот модуль во всех модулях .cpp, которым необходим доступ к объектам этого класса.  
  
 Если `DECLARE_SERIAL` включен в объявление класса, а затем `IMPLEMENT_SERIAL` должны быть включены в реализацию класса.  
  
 `DECLARE_SERIAL` Макрос включает все функциональные возможности `DECLARE_DYNAMIC` и `DECLARE_DYNCREATE`.  
  
 Можно использовать **AFX_API** макрос для автоматического экспорта `CArchive` оператор извлечения для классов, использующих `DECLARE_SERIAL` и `IMPLEMENT_SERIAL` макросы. Группировка объявления класса (находится в h-файл) с помощью следующего кода:  
  
 [!code-cpp[NVC_MFCCObjectSample#20](../../mfc/codesnippet/cpp/run-time-object-model-services_1.h)]  
  
 Дополнительные сведения о `DECLARE_SERIAL` макрос, в разделе [разделы класс CObject](../../mfc/using-cobject.md).  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCCObjectSample#21](../../mfc/codesnippet/cpp/run-time-object-model-services_2.h)]  
  
### <a name="requirements"></a>Требования  
 **Заголовок:** afx.h 

##  <a name="implement_dynamic"></a>  IMPLEMENT_DYNAMIC  
 Создает код C++, необходимые для динамического `CObject`-производного класса во время выполнения доступ к имени класса и положение в иерархии.  
  
```
IMPLEMENT_DYNAMIC(class_name, base_class_name)  
```  
  
### <a name="parameters"></a>Параметры  
 *class_name*  
 Фактическое имя класса.  
  
 `base_class_name`  
 Имя базового класса.  
  
### <a name="remarks"></a>Примечания  
 Используйте `IMPLEMENT_DYNAMIC` макрос в модуль .cpp и свяжите полученный объект кода только один раз.  
  
 Дополнительные сведения см. в разделе [разделы класс CObject](../../mfc/using-cobject.md).  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCCObjectSample#2](../../mfc/codesnippet/cpp/run-time-object-model-services_3.h)]  
  
 [!code-cpp[NVC_MFCCObjectSample#3](../../mfc/codesnippet/cpp/run-time-object-model-services_4.cpp)]  

### <a name="requirements"></a>Требования  
 **Заголовок:** afx.h 

##  <a name="implement_dyncreate"></a>  IMPLEMENT_DYNCREATE  
 Включает объекты `CObject`-производные классы динамически создаваемых при запуске время при использовании с `DECLARE_DYNCREATE` макрос.  
  
```
IMPLEMENT_DYNCREATE(class_name, base_class_name)   
```  
  
### <a name="parameters"></a>Параметры  
 *class_name*  
 Фактическое имя класса.  
  
 `base_class_name`  
 Фактическое имя базового класса.  
  
### <a name="remarks"></a>Примечания  
 Платформа использует эту возможность для создания новых объектов динамически, например, при считывании объекта с диска во время сериализации. Добавить `IMPLEMENT_DYNCREATE` макрос в файле реализации класса. Дополнительные сведения см. в разделе [разделы класс CObject](../../mfc/using-cobject.md).  
  
 Если вы используете `DECLARE_DYNCREATE` и `IMPLEMENT_DYNCREATE` макросов, можно использовать `RUNTIME_CLASS` макрос и `CObject::IsKindOf` функции-члена для определения класса объектов во время выполнения.  
  
 Если `DECLARE_DYNCREATE` включен в объявление класса, а затем `IMPLEMENT_DYNCREATE` должны быть включены в реализацию класса.  
  
 Обратите внимание, что это определение макроса вызывается конструктор по умолчанию для класса. Если нетривиальные конструкторы явно реализован классом, он должен явно реализовать конструктор по умолчанию. Конструктор по умолчанию, которые могут добавляться в класс **закрытый** или **защищенных** член разделы, чтобы предотвратить его вызов из вне реализацию класса.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCCObjectSample#22](../../mfc/codesnippet/cpp/run-time-object-model-services_5.h)]  
  
 [!code-cpp[NVC_MFCCObjectSample#23](../../mfc/codesnippet/cpp/run-time-object-model-services_6.cpp)]  

### <a name="requirements"></a>Требования  
 **Заголовок:** afx.h 

## <a name="implement_olecreate_flags"></a>  IMPLEMENT_OLECREATE_FLAGS
Либо этот макрос или [IMPLEMENT_OLECREATE](#implement_olecreate) должен быть указан в файле реализации для любого класса, который использует `DECLARE_OLECREATE`.  
   
### <a name="syntax"></a>Синтаксис    
```
IMPLEMENT_OLECREATE_FLAGS( class_name, external_name, nFlags, 
    l, w1, w2, b1, b2, b3, b4, b5, b6, b7, b8)  
  
```
### <a name="parameters"></a>Параметры  
 *class_name*  
 Фактическое имя класса.  
  
 *Параметры external_name*  
 Имя объекта, другим приложениям (заключенная в кавычки).  
  
 `nFlags`  
 Содержит один или несколько из следующих флагов:  
  
-   `afxRegInsertable` Позволяет элементу управления отображаются в диалоговом окне Вставка объекта OLE-объекты.    
-   `afxRegApartmentThreading` Задает модель потоков в реестре, ThreadingModel = подразделения.    
-   **afxRegFreeThreading** задает потоковую модель в реестре, ThreadingModel = Free.  
  
     Можно объединить два флага `afxRegApartmentThreading` и `afxRegFreeThreading` для задания ThreadingModel = Both. В разделе [InprocServer32](http://msdn.microsoft.com/library/windows/desktop/ms682390) в Windows SDK, Дополнительные сведения о потоковой модели регистрации.    
 *l*, *w1*, *w2*, *b1*, *В2*, *b3*, *b4* , *b5*, *b6*, *b7*, *b8*  
 Компоненты класса **CLSID**.  
   
### <a name="remarks"></a>Примечания  
  
> [!NOTE]
>  Если вы используете `IMPLEMENT_OLECREATE_FLAGS`, можно указать, какие потоковой модели, поддерживаемые объектом с помощью `nFlags` параметра. Для поддержки только treading одной модели, используйте `IMPLEMENT_OLECREATE`.  
  
 Внешнее имя является идентификатором, другим приложениям. Клиентские приложения используют внешнее имя для запроса объекта данного класса сервера автоматизации.  
  
 Идентификатор класса OLE имеет уникальный 128-разрядный идентификатор для объекта. Он состоит из одного **длинные**, два **WORD**s и восьми **БАЙТОВ**s, представленные как *l*, *w1*, *w2*, и *b1* через *b8* в описании синтаксиса. Мастер приложения и код мастеров при необходимости создать уникальные идентификаторы класса OLE для вас.  
   
### <a name="requirements"></a>Требования  
 **Заголовок:** afxdisp.h  
   
### <a name="see-also"></a>См. также  
 [Макросы и глобальные объекты](mfc-macros-and-globals.md)   
 [DECLARE_OLECREATE](#declare_olecreate)   
 [Раздел CLSID](http://msdn.microsoft.com/library/windows/desktop/ms691424)


## <a name="implement_olecreate"></a> IMPLEMENT_OLECTLTYPE
Реализует **GetUserTypeNameID** и `GetMiscStatus` функции-члены класса элемента управления.  
   
### <a name="syntax"></a>Синтаксис    
```
DECLARE_OLECTLTYPE( class_name, idsUserTypeName, dwOleMisc )  
```
### <a name="parameters"></a>Параметры  
 *class_name*  
 Имя класса элемента управления.  
  
 *idsUserTypeName*  
 Идентификатор ресурса строка, содержащая имя внешнего элемента управления.  
  
 *dwOleMisc*  
 Перечисление, содержащее один или несколько флагов. Дополнительные сведения об этом перечислении см. в разделе [OLEMISC, ПОЗВОЛЯЯ](http://msdn.microsoft.com/library/windows/desktop/ms678497) в Windows SDK.  
   
### <a name="remarks"></a>Примечания  
 В дополнение к `IMPLEMENT_OLECTLTYPE`, необходимо добавить **DECLARE_OLECTLTYPE** макрос к объявлению класса элемента управления.  
  
 **GetUserTypeNameID** функция-член возвращает строку ресурса, определяющий класса элемента управления. `GetMiscStatus` Возвращает **OLEMISC, ПОЗВОЛЯЯ** bits для элемента управления. Это перечисление указывает набор параметров, определяющих различные характеристики элемента управления. Полное описание **OLEMISC, ПОЗВОЛЯЯ** параметров, в разделе [OLEMISC, ПОЗВОЛЯЯ](http://msdn.microsoft.com/library/windows/desktop/ms678497) в Windows SDK.  
  
> [!NOTE]
>  Настройки по умолчанию, используемые автоматически ActiveX: **OLEMISC_ACTIVATEWHENVISIBLE**, **OLEMISC_SETCLIENTSITEFIRST**, **OLEMISC_INSIDEOUT**, **OLEMISC_CANTLINKINSIDE**, и **OLEMISC_RECOMPOSEONRESIZE**.  
   
### <a name="requirements"></a>Требования  
 **Заголовок:** afxctl.h  
   
### <a name="see-also"></a>См. также  
 [Макросы и глобальные объекты](mfc-macros-and-globals.md)   
 [DECLARE_OLECTLTYPE](#declare_olectltype)

##  <a name="implement_serial"></a>  IMPLEMENT_SERIAL  
 Создает код C++, необходимые для динамического `CObject`-производного класса во время выполнения доступ к имени класса и положение в иерархии.  
  
```
IMPLEMENT_SERIAL(class_name, base_class_name, wSchema)  
```  
  
### <a name="parameters"></a>Параметры  
 *class_name*  
 Фактическое имя класса.  
  
 `base_class_name`  
 Имя базового класса.  
  
 *wSchema*  
 Объект **UINT** «номер версии», который кодируется в архиве, чтобы включить программу десериализации для идентификации и обработки данных, созданных ранее программы версии. Номер схемы класса не должен быть -1.  
  
### <a name="remarks"></a>Примечания  
 Используйте `IMPLEMENT_SERIAL` макрос в модуле .cpp; свяжите результирующий код объекта только один раз.  
  
 Можно использовать **AFX_API** макрос для автоматического экспорта `CArchive` оператор извлечения для классов, использующих `DECLARE_SERIAL` и `IMPLEMENT_SERIAL` макросы. Группировка объявления класса (находится в h-файл) с помощью следующего кода:  
  
 [!code-cpp[NVC_MFCCObjectSample#20](../../mfc/codesnippet/cpp/run-time-object-model-services_1.h)]  
  
 Дополнительные сведения см. в разделе [разделы класс CObject](../../mfc/using-cobject.md).  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCCObjectSample#24](../../mfc/codesnippet/cpp/run-time-object-model-services_7.cpp)]  

### <a name="requirements"></a>Требования  
 **Заголовок:** afx.h 

##  <a name="runtime_class"></a>  RUNTIME_CLASS  
 Возвращает структуру класса среды выполнения от имени для класса C++.  
  
```
RUNTIME_CLASS(class_name)  
```  
  
### <a name="parameters"></a>Параметры  
 *class_name*  
 Фактическое имя класса (не заключен в кавычки).  
  
### <a name="remarks"></a>Примечания  
 `RUNTIME_CLASS` Возвращает указатель на [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) структура для класса, указанного параметром *class_name*. Только `CObject`-производных классов, объявленные с `DECLARE_DYNAMIC`, `DECLARE_DYNCREATE`, или `DECLARE_SERIAL` возвращает указатели на `CRuntimeClass` структуры.  
  
 Дополнительные сведения см. в разделе [разделы класс CObject](../../mfc/using-cobject.md).  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCCObjectSample#25](../../mfc/codesnippet/cpp/run-time-object-model-services_8.cpp)]  

### <a name="requirements"></a>Требования  
 **Заголовок:** afx.h 
   
##  <a name="declare_olecreate"></a>  DECLARE_OLECREATE  
 Включает объекты `CCmdTarget`-производные классы для создания с помощью OLE-автоматизации.  
  
```
DECLARE_OLECREATE(class_name) 
```  
  
### <a name="parameters"></a>Параметры  
 *class_name*  
 Фактическое имя класса.  
  
### <a name="remarks"></a>Примечания  
 Этот макрос включает другие OLE-приложения для создания объектов этого типа.  
  
 Добавить `DECLARE_OLECREATE` макрос в модуле .h для класса, а затем включить этот модуль во всех модулях .cpp, которым необходим доступ к объектам этого класса.  
  
 Если `DECLARE_OLECREATE` включен в объявление класса, а затем `IMPLEMENT_OLECREATE` должны быть включены в реализацию класса. Объявление класса с помощью `DECLARE_OLECREATE` также должна использовать `DECLARE_DYNCREATE` или `DECLARE_SERIAL`.  

### <a name="requirements"></a>Требования  
 **Заголовок**: afxdisp.h  

##  <a name="implement_olecreate"></a>  IMPLEMENT_OLECREATE  
 Либо этот макрос или [IMPLEMENT_OLECREATE_FLAGS](#implement_olecreate_flags) должен быть указан в файле реализации для любого класса, который использует `DECLARE_OLECREATE`.  
  
```
IMPLEMENT_OLECREATE(class_name, external_name, l, w1, w2, b1, b2, b3, b4, b5, b6, b7, b8)  
```  
  
### <a name="parameters"></a>Параметры  
 *class_name*  
 Фактическое имя класса.  
  
 *Параметры external_name*  
 Имя объекта, другим приложениям (заключенная в кавычки).  
  
 *l*, *w1*, *w2*, *b1*, *В2*, *b3*, *b4* , *b5*, *b6*, *b7*, *b8*  
 Компоненты класса **CLSID**.  
  
### <a name="remarks"></a>Примечания  
  
> [!NOTE]
>  Если вы используете `IMPLEMENT_OLECREATE`, по умолчанию поддерживает только один потоковую модель. Если вы используете `IMPLEMENT_OLECREATE_FLAGS`, можно указать, какие потоковой модели, поддерживаемые объектом с помощью `nFlags` параметра.  
  
 Внешнее имя является идентификатором, другим приложениям. Клиентские приложения используют внешнее имя для запроса объекта данного класса сервера автоматизации.  
  
 Идентификатор класса OLE имеет уникальный 128-разрядный идентификатор для объекта. Он состоит из одного **длинные**, два **WORD**s и восьми **БАЙТОВ**s, представленные как *l*, *w1*, *w2*, и *b1* через *b8* в описании синтаксиса. Мастер приложения и код мастеров при необходимости создать уникальные идентификаторы класса OLE для вас.  

### <a name="requirements"></a>Требования  
 **Заголовок**: afxdisp.h 

## <a name="see-also"></a>См. также  
 [Макросы и глобальные объекты](../../mfc/reference/mfc-macros-and-globals.md)

