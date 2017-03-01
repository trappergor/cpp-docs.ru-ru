---
title: "Службы модели объекта во время выполнения | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vc.mfc.macros
dev_langs:
- C++
helpviewer_keywords:
- run-time object model services macros
ms.assetid: 4a3e79df-2ee3-43a4-8193-20298828de85
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
ms.openlocfilehash: 8739201489644b0f1695a70d0dc12d04ca47aa68
ms.lasthandoff: 02/24/2017

---
# <a name="run-time-object-model-services"></a>Службы модели объекта во время выполнения
Классы [CObject](../../mfc/reference/cobject-class.md) и [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) инкапсулировать несколько служб объектов, включая доступ к сведения о классе во время выполнения, сериализации и динамическое создание объектов. Все классы, производные от `CObject` наследуют эти функциональные возможности.  
  
 Доступ к данным класса во время выполнения позволяет определить сведения о классе объекта во время выполнения. Возможность определения класса объекта во время выполнения полезно, когда требуется дополнительный проверку типов аргументов функции, а также когда необходимо написать код специального назначения, на основе класса объекта. Сведения о классе во время выполнения не поддерживается языком C++.  
  
 Сериализация — это процесс записи или чтению содержимое объекта в или из файла. Можно использовать сериализацию для хранения содержимого объекта даже после выхода из приложения. Объект может считываться из файла при перезапуске приложения. Такие объекты данных, называются «постоянный».  
  
 Динамическое создание объектов позволяет создать объект из указанного класса во время выполнения. Например документов, представления и объекты кадр должен поддерживать динамическое создание благодаря платформе для динамического создания.  
  
 В следующей таблице перечислены макросы MFC, которые поддерживают сведения о классе во время выполнения, сериализации и динамическое создание.  
  
 Дополнительные сведения об этих служб объектов во время выполнения и сериализации см. в статье [класс CObject: сведения о классе во время выполнения доступ к](../../mfc/accessing-run-time-class-information.md).  
  
### <a name="run-time-object-model-services-macros"></a>Макросы служб времени выполнения объектной модели  
  
|||  
|-|-|  
|[DECLARE_DYNAMIC](#declare_dynamic)|Обеспечивает доступ к сведения о классе во время выполнения (необходимо использовать в объявлении класса).|  
|[DECLARE_DYNCREATE](#declare_dyncreate)|Обеспечивает динамическое создание и доступ к данным класса во время выполнения (необходимо использовать в объявлении класса).|  
|[DECLARE_SERIAL](#declare_serial)|Позволяет сериализацию и доступ к данным класса во время выполнения (необходимо использовать в объявлении класса).|  
|[IMPLEMENT_DYNAMIC](#implement_dynamic)|Обеспечивает доступ к сведения о классе во время выполнения (необходимо использовать реализацию класса).|  
|[IMPLEMENT_DYNCREATE](#implement_dyncreate)|Обеспечивает динамическое создание и доступ к данным во время выполнения (необходимо использовать реализацию класса).|  
|[IMPLEMENT_SERIAL](#implement_serial)|Разрешает сериализацию и доступ к данным класса во время выполнения (необходимо использовать реализацию класса).|  
|[RUNTIME_CLASS](#runtime_class)|Возвращает `CRuntimeClass` структуры, относящейся к именованному классу.|  


 OLE часто требуется динамическое создание объектов во время выполнения. Например приложение OLE-сервера должен быть динамически создаваемого OLE-элементы в ответ на запрос от клиента. Аналогично сервер автоматизации должна быть возможность создавать элементы в ответ на запросы от клиентов автоматизации.  
  
 Библиотеки классов Microsoft Foundation предоставляет два макроса конкретных OLE.  
  
### <a name="dynamic-creation-of-ole-objects"></a>Динамическое создание объектов OLE  
  
|||  
|-|-|  
|[DECLARE_OLECREATE](#declare_olecreate)|Позволяет объектам для создания с помощью OLE-автоматизации.|  
|[IMPLEMENT_OLECREATE](#implement_olecreate)|Позволяет объектам, создаваемых системой OLE.|  
  
##  <a name="a-namedeclaredynamica--declaredynamic"></a><a name="declare_dynamic"></a>DECLARE_DYNAMIC  
 Добавляет возможность доступа к среде выполнения сведения о классе объекта при наследовании от класса `CObject`.  
  
```
DECLARE_DYNAMIC(class_name) 
```  
  
### <a name="parameters"></a>Параметры  
 *class_name*  
 Фактическое имя класса.  
  
### <a name="remarks"></a>Примечания  
 Добавление `DECLARE_DYNAMIC` макрос в модуль заголовков (.h) для класса, включите этот модуль во всех модулях .cpp, которым требуется доступ к объектам этого класса.  
  
 При использовании **DECLARE**_ **динамическое** и `IMPLEMENT_DYNAMIC` макросов, как описано, можно использовать `RUNTIME_CLASS` макрос и `CObject::IsKindOf` функции, чтобы определить класс объектов во время выполнения.  
  
 Если `DECLARE_DYNAMIC` включен в объявление класса, затем `IMPLEMENT_DYNAMIC` должны быть включены в реализацию класса.  
  
 Дополнительные сведения о `DECLARE_DYNAMIC` макрос, в разделе [разделы с описанием классов от CObject](../../mfc/using-cobject.md).  
  
### <a name="example"></a>Пример  
 В примере показано [IMPLEMENT_DYNAMIC](#implement_dynamic).  

### <a name="requirements"></a>Требования  
 **Заголовок:** afx.h 

##  <a name="a-namedeclaredyncreatea--declaredyncreate"></a><a name="declare_dyncreate"></a>DECLARE_DYNCREATE  
 Включает объекты `CObject`-производных классов создается динамически во время выполнения.  
  
```
DECLARE_DYNCREATE(class_name)   
```  
  
### <a name="parameters"></a>Параметры  
 *class_name*  
 Фактическое имя класса.  
  
### <a name="remarks"></a>Примечания  
 Платформа использует эту возможность для динамического создания новых объектов. Например новое представление создается при открытии документа. Кадр классы документов, представления и должен поддерживать динамическое создание так как платформа требуется динамическое создание.  
  
 Добавление `DECLARE_DYNCREATE` макрос в модуле .h для класса, включите этот модуль во всех модулях .cpp, которым требуется доступ к объектам этого класса.  
  
 Если `DECLARE_DYNCREATE` включен в объявление класса, затем `IMPLEMENT_DYNCREATE` должны быть включены в реализацию класса.  
  
 Дополнительные сведения о `DECLARE_DYNCREATE` макрос, в разделе [разделы с описанием классов от CObject](../../mfc/using-cobject.md).  
  
> [!NOTE]
>  `DECLARE_DYNCREATE` Макрос включает все функциональные возможности `DECLARE_DYNAMIC`.  
  
### <a name="example"></a>Пример  
 В примере показано [IMPLEMENT_DYNCREATE](#implement_dyncreate).  

### <a name="requirements"></a>Требования  
 **Заголовок:** afx.h 

##  <a name="a-namedeclareseriala--declareserial"></a><a name="declare_serial"></a>DECLARE_SERIAL  
 Создает заголовок код C++, необходимые для `CObject`-производного класса, который может быть сериализован.  
  
```
DECLARE_SERIAL(class_name)   
```  
  
### <a name="parameters"></a>Параметры  
 *class_name*  
 Фактическое имя класса.  
  
### <a name="remarks"></a>Примечания  
 Сериализация — это процесс записи или чтению содержимое объекта в и из файла.  
  
 Используйте `DECLARE_SERIAL` макрос в модуле .h, а затем добавить этот модуль во всех модулях .cpp, которым требуется доступ к объектам этого класса.  
  
 Если `DECLARE_SERIAL` включен в объявление класса, затем `IMPLEMENT_SERIAL` должны быть включены в реализацию класса.  
  
 `DECLARE_SERIAL` Макрос включает все функциональные возможности `DECLARE_DYNAMIC` и `DECLARE_DYNCREATE`.  
  
 Можно использовать **AFX_API** макрос для автоматического экспорта `CArchive` оператор извлечения для классов, использующих `DECLARE_SERIAL` и `IMPLEMENT_SERIAL` макросы. Квадратная скобка объявления класса (находится в h-файл) с помощью следующего кода:  
  
 [!code-cpp[NVC_MFCCObjectSample&20;](../../mfc/codesnippet/cpp/run-time-object-model-services_1.h)]  
  
 Дополнительные сведения о `DECLARE_SERIAL` макрос, в разделе [разделы с описанием классов от CObject](../../mfc/using-cobject.md).  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCCObjectSample&#21;](../../mfc/codesnippet/cpp/run-time-object-model-services_2.h)]  
  
### <a name="requirements"></a>Требования  
 **Заголовок:** afx.h 

##  <a name="a-nameimplementdynamica--implementdynamic"></a><a name="implement_dynamic"></a>IMPLEMENT_DYNAMIC  
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
 Используйте `IMPLEMENT_DYNAMIC` макрос в .cpp модуля, а затем ссылку результирующий объект кода только один раз.  
  
 Дополнительные сведения см. в разделе [разделы с описанием классов от CObject](../../mfc/using-cobject.md).  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCCObjectSample&#2;](../../mfc/codesnippet/cpp/run-time-object-model-services_3.h)]  
  
 [!code-cpp[NVC_MFCCObjectSample&#3;](../../mfc/codesnippet/cpp/run-time-object-model-services_4.cpp)]  

### <a name="requirements"></a>Требования  
 **Заголовок:** afx.h 

##  <a name="a-nameimplementdyncreatea--implementdyncreate"></a><a name="implement_dyncreate"></a>IMPLEMENT_DYNCREATE  
 Включает объекты `CObject`-производных классов создается динамически при запуске время при использовании `DECLARE_DYNCREATE` макрос.  
  
```
IMPLEMENT_DYNCREATE(class_name, base_class_name)   
```  
  
### <a name="parameters"></a>Параметры  
 *class_name*  
 Фактическое имя класса.  
  
 `base_class_name`  
 Фактическое имя базового класса.  
  
### <a name="remarks"></a>Примечания  
 Эта возможность используется платформа для создания новых объектов динамически, например, при считывании объекта с диска во время сериализации. Добавление `IMPLEMENT_DYNCREATE` макрос в файле реализации класса. Дополнительные сведения см. в разделе [разделы с описанием классов от CObject](../../mfc/using-cobject.md).  
  
 Если вы используете `DECLARE_DYNCREATE` и `IMPLEMENT_DYNCREATE` макросы, можно использовать `RUNTIME_CLASS` макрос и `CObject::IsKindOf` функции-члена для определения класса объектов во время выполнения.  
  
 Если `DECLARE_DYNCREATE` включен в объявление класса, затем `IMPLEMENT_DYNCREATE` должны быть включены в реализацию класса.  
  
 Обратите внимание, что это определение макроса вызывается конструктор по умолчанию для класса. Если нетривиальный конструктор явно реализован классом, он должен явным образом реализовать конструктор по умолчанию. Конструктор по умолчанию можно добавить к классу **частного** или **защищенных** член разделы, чтобы предотвратить его вызов из вне реализации класса.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCCObjectSample&#22;](../../mfc/codesnippet/cpp/run-time-object-model-services_5.h)]  
  
 [!code-cpp[NVC_MFCCObjectSample&#23;](../../mfc/codesnippet/cpp/run-time-object-model-services_6.cpp)]  

### <a name="requirements"></a>Требования  
 **Заголовок:** afx.h 

##  <a name="a-nameimplementseriala--implementserial"></a><a name="implement_serial"></a>IMPLEMENT_SERIAL  
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
 Объект **UINT** «номер версии», который кодируется в архиве, чтобы включить программу десериализации для идентификации и обработки данных, созданных ранее программы версии. Номер схемы класса не должен быть указан «1.  
  
### <a name="remarks"></a>Примечания  
 Используйте `IMPLEMENT_SERIAL` макрос в модуле .cpp; свяжите результирующий код объекта только один раз.  
  
 Можно использовать **AFX_API** макрос для автоматического экспорта `CArchive` оператор извлечения для классов, использующих `DECLARE_SERIAL` и `IMPLEMENT_SERIAL` макросы. Квадратная скобка объявления класса (находится в h-файл) с помощью следующего кода:  
  
 [!code-cpp[NVC_MFCCObjectSample&20;](../../mfc/codesnippet/cpp/run-time-object-model-services_1.h)]  
  
 Дополнительные сведения см. в разделе [разделы с описанием классов от CObject](../../mfc/using-cobject.md).  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCCObjectSample&#24;](../../mfc/codesnippet/cpp/run-time-object-model-services_7.cpp)]  

### <a name="requirements"></a>Требования  
 **Заголовок:** afx.h 

##  <a name="a-nameruntimeclassa--runtimeclass"></a><a name="runtime_class"></a>RUNTIME_CLASS  
 Возвращает структуру классов времени выполнения от имени класса C++.  
  
```
RUNTIME_CLASS(class_name)  
```  
  
### <a name="parameters"></a>Параметры  
 *class_name*  
 Фактическое имя класса (не заключен в кавычки).  
  
### <a name="remarks"></a>Примечания  
 `RUNTIME_CLASS`Возвращает указатель на [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) структура для класса, указанного параметром *class_name*. Только `CObject`-производных классов, объявленные с `DECLARE_DYNAMIC`, `DECLARE_DYNCREATE`, или `DECLARE_SERIAL` возвращает указатели на `CRuntimeClass` структуры.  
  
 Дополнительные сведения см. в разделе [разделы с описанием классов от CObject](../../mfc/using-cobject.md).  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCCObjectSample&#25;](../../mfc/codesnippet/cpp/run-time-object-model-services_8.cpp)]  

### <a name="requirements"></a>Требования  
 **Заголовок:** afx.h 
   
##  <a name="a-namedeclareolecreatea--declareolecreate"></a><a name="declare_olecreate"></a>DECLARE_OLECREATE  
 Включает объекты `CCmdTarget`-производные классы для создания с помощью OLE-автоматизации.  
  
```
DECLARE_OLECREATE(class_name) 
```  
  
### <a name="parameters"></a>Параметры  
 *class_name*  
 Фактическое имя класса.  
  
### <a name="remarks"></a>Примечания  
 Этот макрос включает другие OLE-приложения для создания объектов этого типа.  
  
 Добавить `DECLARE_OLECREATE` макрос в модуле .h для класса, а затем добавить этот модуль во всех модулях .cpp, которым требуется доступ к объектам этого класса.  
  
 Если `DECLARE_OLECREATE` включен в объявление класса, затем `IMPLEMENT_OLECREATE` должны быть включены в реализацию класса. Объявление класса с помощью `DECLARE_OLECREATE` также должна использовать `DECLARE_DYNCREATE` или `DECLARE_SERIAL`.  

### <a name="requirements"></a>Требования  
 **Заголовок**: afxdisp.h  

##  <a name="a-nameimplementolecreatea--implementolecreate"></a><a name="implement_olecreate"></a>IMPLEMENT_OLECREATE  
 Либо этот макрос или [IMPLEMENT_OLECREATE_FLAGS](http://msdn.microsoft.com/library/d1589f6a-5a69-4742-b07c-4c621cfd040d) должен присутствовать в файле реализации для любого класса, который использует `DECLARE_OLECREATE`.  
  
```
IMPLEMENT_OLECREATE(class_name, external_name, l, w1, w2, b1, b2, b3, b4, b5, b6, b7, b8)  
```  
  
### <a name="parameters"></a>Параметры  
 *class_name*  
 Фактическое имя класса.  
  
 *параметр external_name*  
 Имя объекта, другим приложениям (заключенная в кавычки).  
  
 *l*, *w1*, *w2*, *b1*, *b2*, *b3*, *b4*, *b5*, *b6*, *b7*, *b8*  
 Компоненты класса **CLSID**.  
  
### <a name="remarks"></a>Примечания  
  
> [!NOTE]
>  При использовании `IMPLEMENT_OLECREATE`, по умолчанию поддерживают только однопотоковую модель. Если вы используете `IMPLEMENT_OLECREATE_FLAGS`, можно указать, какие потоковой модели, поддерживаемые объектом с помощью `nFlags` параметр.  
  
 Внешнее имя является идентификатором, другим приложениям. Клиентские приложения используют внешнее имя для запроса объекта этого класса из сервера автоматизации.  
  
 Идентификатор класса OLE имеет уникальный 128-разрядный идентификатор для объекта. Он состоит из одного **длинные**, два **WORD**s и восемь **БАЙТОВ**s, представленные как *l*, *w1*, *w2*, и *b1* через *b8* в описании синтаксиса. Мастера приложений и кода мастера при необходимости создать уникальные идентификаторы класса OLE для вас.  

### <a name="requirements"></a>Требования  
 **Заголовок**: afxdisp.h 

## <a name="see-also"></a>См. также  
 [Макросы и глобальные объекты](../../mfc/reference/mfc-macros-and-globals.md)

