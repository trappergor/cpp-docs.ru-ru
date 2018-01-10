---
title: "Съемы | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vc.mfc.macros.maps
dev_langs: C++
helpviewer_keywords:
- dispatch maps [MFC], macros
- dispatch maps [MFC]
- dispatch map macros [MFC]
ms.assetid: bef9d08b-ad35-4c3a-99d8-04150c7c04e2
caps.latest.revision: "14"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 3112c092a4e1d6eb970fb50153c543baa98ee853
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="dispatch-maps"></a>Схемы подготовки к отправке
OLE-автоматизации предоставляет способы для вызова методов и для доступа к свойствам в приложениях. «Схеме диспетчеризации,» представляет внутренние и внешние имена функций объектов и свойств, а также типы данных, сами свойства и представляет собой механизм, предоставляемый библиотеки классов Microsoft Foundation для диспетчеризации эти запросы аргументы функции.  
  
### <a name="dispatch-maps"></a>Схемы подготовки к отправке  
  
|||  
|-|-|  
|[DECLARE_DISPATCH_MAP](#declare_dispatch_map)|Объявляет, что карту диспетчеризации будет использоваться для предоставляют методы и свойства (следует использовать в объявлении класса) класса.|  
|[BEGIN_DISPATCH_MAP](#begin_dispatch_map)|Начинается определение карту диспетчеризации.|  
|[END_DISPATCH_MAP](#end_dispatch_map)|Завершает определение карту диспетчеризации.|  
|[DISP_FUNCTION](#disp_function)|Используется для распределения карты для определения функцию автоматизации OLE.|  
|[DISP_PROPERTY](#disp_property)|Определяет свойство автоматизации OLE.|  
|[DISP_PROPERTY_EX](#disp_property_ex)|Определяет свойство автоматизации OLE и имен функций Get и Set.|  
|[DISP_PROPERTY_NOTIFY](#disp_property_notify)|Определяет свойство автоматизации OLE с уведомлением.|  
|[DISP_PROPERTY_PARAM](#disp_property_param)|Определяет свойство автоматизации OLE, который принимает параметры и имена функций Get и Set.|  
|[DISP_DEFVALUE](#disp_defvalue)|Делает существующего свойства объекта, значение по умолчанию.|  
  
##  <a name="declare_dispatch_map"></a>DECLARE_DISPATCH_MAP  
 Если `CCmdTarget`-производный класс в программе поддерживает OLE-автоматизации, что класс должен предоставлять карту диспетчеризации для предоставления его методы и свойства.  
  
```   
DECLARE_DISPATCH_MAP()  
```  
  
### <a name="remarks"></a>Примечания  
 Используйте `DECLARE_DISPATCH_MAP` макрос в конце объявления класса. Затем в. CPP-файл, определяющий член, функции для класса, используйте `BEGIN_DISPATCH_MAP` макрос. Затем включить макрос записи для каждого класса предоставленные методы и свойства ( `DISP_FUNCTION`, `DISP_PROPERTY`и так далее). Наконец, используйте `END_DISPATCH_MAP` макрос.  
  
> [!NOTE]
>  При объявлении членов после `DECLARE_DISPATCH_MAP`, необходимо указать новый тип доступа ( **открытый**, `private`, или `protected`) для них.  
  
 Мастера мастер приложения и код помочь в создании классов автоматизации и обслуживание схемы подготовки к отправке. Дополнительные сведения для подготовки к отправке карт см. в разделе [серверы автоматизации](../../mfc/automation-servers.md).  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCAutomation#10](../../mfc/codesnippet/cpp/dispatch-maps_1.h)]  

### <a name="requirements"></a>Требования  
 **Заголовок:** afxwin.h  

##  <a name="begin_dispatch_map"></a>BEGIN_DISPATCH_MAP  
 Объявляет определение карту диспетчеризации.  
  
```  
BEGIN_DISPATCH_MAP(theClass, baseClass)   
```  
  
### <a name="parameters"></a>Параметры  
 `theClass`  
 Задает имя класса, который является владельцем этой карте диспетчеризации.  
  
 `baseClass`  
 Указывает имя базового класса `theClass`.  
  
### <a name="remarks"></a>Примечания  
 В файле реализации (CPP), который определяет функции-члены класса, запустить карту диспетчеризации с `BEGIN_DISPATCH_MAP` макрос, добавить макрос записи для каждой функции распределения и свойств и завершения карту диспетчеризации с `END_DISPATCH_MAP` макрос.  

### <a name="requirements"></a>Требования  
 **Заголовок:** afxdisp.h  

##  <a name="end_dispatch_map"></a>END_DISPATCH_MAP  
 Завершает определение карту диспетчеризации.  
  
```   
END_DISPATCH_MAP()  
```  
  
### <a name="remarks"></a>Примечания  
 Он должен использоваться в сочетании с `BEGIN_DISPATCH_MAP`.  

### <a name="requirements"></a>Требования  
 **Заголовок:** afxdisp.h  

##  <a name="disp_function"></a>DISP_FUNCTION  
 Определяет функцию автоматизации OLE в карту диспетчеризации.  
  
```   
DISP_FUNCTION(
  theClass, 
  pszName, 
  pfnMember, 
  vtRetVal, 
  vtsParams)   
```  
  
### <a name="parameters"></a>Параметры  
 `theClass`  
 Имя класса.  
  
 `pszName`  
 Внешнее имя функции.  
  
 `pfnMember`  
 Имя функции-члена.  
  
 `vtRetVal`  
 Значение, указывающее тип возвращаемого значения функции.  
  
 `vtsParams`  
 Разделенный пробелами список из одной или нескольких констант, указав список параметров функции.  
  
### <a name="remarks"></a>Примечания  
 `vtRetVal` Аргумент имеет тип **VARTYPE**. Следующие возможные значения для этого аргумента, взяты из `VARENUM` перечисления:  
  
|Символ|Тип возвращаемого значения|  
|------------|-----------------|  
|`VT_EMPTY`|`void`|  
|`VT_I2`|**short**|  
|`VT_I4`|**long**|  
|`VT_R4`|**float**|  
|`VT_R8`|**double**|  
|`VT_CY`|**CY**|  
|`VT_DATE`|**DATE**|  
|`VT_BSTR`|`BSTR`|  
|**VT_DISPATCH**|`LPDISPATCH`|  
|`VT_ERROR`|`SCODE`|  
|`VT_BOOL`|**BOOL**|  
|**VT_VARIANT**|**VARIANT**|  
|**VT_UNKNOWN**|`LPUNKNOWN`|  
  
 `vtsParams` Аргумент является разделенный пробелами список значений из **VTS_** константы. Один или несколько из следующих значений, разделенных пробелами (не запятыми) Указывает список параметров функции. Например, примененная к объекту директива 
  
 [!code-cpp[NVC_MFCAutomation#14](../../mfc/codesnippet/cpp/dispatch-maps_2.cpp)]  
  
 Указывает список, содержащий короткое целое число, следуют указателя в короткое целое число.  
  
 **VTS_** константы имеют следующим образом:  
  
|Символ|Тип параметра|  
|------------|--------------------|  
|**VTS_I2**|`Short`|  
|**VTS_I4**|`Long`|  
|**VTS_R4**|**Float**|  
|**VTS_R8**|`Double`|  
|**VTS_CY**|**const CY** или **CY\***|  
|**VTS_DATE**|**DATE**|  
|**VTS_BSTR**|`LPCSTR`|  
|**VTS_DISPATCH**|`LPDISPATCH`|  
|**VTS_SCODE**|`SCODE`|  
|**VTS_BOOL**|**BOOL**|  
|**VTS_VARIANT**|**const VARIANT\***  или **VARIANT &**|  
|**VTS_UNKNOWN**|`LPUNKNOWN`|  
|**VTS_PI2**|**короткий\***|  
|**VTS_PI4**|**Long\***|  
|**VTS_PR4**|**число с плавающей запятой\***|  
|**VTS_PR8**|**Double\***|  
|**VTS_PCY**|**CY\***|  
|**VTS_PDATE**|**ДАТА\***|  
|**VTS_PBSTR**|**BSTR\***|  
|**VTS_PDISPATCH**|**LPDISPATCH\***|  
|**VTS_PSCODE**|**SCODE\***|  
|**VTS_PBOOL**|**BOOL\***|  
|**VTS_PVARIANT**|**VARIANT\***|  
|**VTS_PUNKNOWN**|**LPUNKNOWN\***|  
|**VTS_NONE**|Без параметров|  

### <a name="requirements"></a>Требования  
 **Заголовок:** afxdisp.h 

##  <a name="disp_property"></a>DISP_PROPERTY  
 Определяет свойства метода OLE-автоматизации в карту диспетчеризации.  
  
```   
DISP_PROPERTY(
  theClass, 
  pszName, 
  memberName, 
  vtPropType)   
```  
  
### <a name="parameters"></a>Параметры  
 `theClass`  
 Имя класса.  
  
 `pszName`  
 Внешнее имя свойства.  
  
 `memberName`  
 Имя переменной-члена, в котором хранится свойство.  
  
 `vtPropType`  
 Значение, указывающее тип свойства.  
  
### <a name="remarks"></a>Примечания  
 `vtPropType` Аргумент имеет тип **VARTYPE**. Возможные значения для этого аргумента, взяты из `VARENUM` перечисления:  
  
|Символ|**Тип свойства**|  
|------------|-----------------------|  
|`VT_I2`|**short**|  
|`VT_I4`|**long**|  
|`VT_R4`|**float**|  
|`VT_R8`|**double**|  
|`VT_CY`|**CY**|  
|`VT_DATE`|**DATE**|  
|`VT_BSTR`|`CString`|  
|**VT_DISPATCH**|`LPDISPATCH`|  
|`VT_ERROR`|`SCODE`|  
|`VT_BOOL`|**BOOL**|  
|**VT_VARIANT**|**VARIANT**|  
|**VT_UNKNOWN**|`LPUNKNOWN`|  
  
 При изменении свойства, значение переменной-члена, заданные в внешнего клиента `memberName` изменяет; нет уведомления об изменении.  

### <a name="requirements"></a>Требования  
 **Заголовок:** afxdisp.h 

##  <a name="disp_property_ex"></a>DISP_PROPERTY_EX  
 Определяет свойство автоматизации OLE и имя функции, используемые для получения и задания значения свойства в карту диспетчеризации.  
  
```   
DISP_PROPERTY_EX(
  theClass, 
  pszName, 
  memberGet, 
  memberSet, 
  vtPropType)   
```  
  
### <a name="parameters"></a>Параметры  
 `theClass`  
 Имя класса.  
  
 `pszName`  
 Внешнее имя свойства.  
  
 `memberGet`  
 Имя функции-члена, используемый для получения свойства.  
  
 `memberSet`  
 Имя функции-члена, используемый для задания свойства.  
  
 `vtPropType`  
 Значение, указывающее тип свойства.  
  
### <a name="remarks"></a>Примечания  
 `memberGet` И `memberSet` функции имеют подписи определяется `vtPropType` аргумент. `memberGet` Функция не принимает аргументы и возвращает значение типа, указанного параметром `vtPropType`. `memberSet` Функция принимает аргумент типа, заданного параметром `vtPropType` и не возвращает никаких данных.  
  
 `vtPropType` Аргумент имеет тип **VARTYPE**. Возможные значения для этого аргумента, взяты из `VARENUM` перечисления. Список этих значений см `vtRetVal` параметр в [DISP_FUNCTION](#disp_function). Обратите внимание, что `VT_EMPTY`, упомянутую в `DISP_FUNCTION` примечания, запрещается использовать как тип данных свойства.  

### <a name="requirements"></a>Требования  
 **Заголовок:** afxdisp.h 

##  <a name="disp_property_notify"></a>DISP_PROPERTY_NOTIFY  
 Определяет свойство автоматизации OLE с уведомлением в карту диспетчеризации.  
  
```   
DISP_PROPERTY_NOTIFY(
  theClass, 
  szExternalName, 
  memberName, 
  pfnAfterSet, 
  vtPropType)   
```  
  
### <a name="parameters"></a>Параметры  
 `theClass`  
 Имя класса.  
  
 `szExternalName`  
 Внешнее имя свойства.  
  
 `memberName`  
 Имя переменной-члена, в котором хранится свойство.  
  
 `pfnAfterSet`  
 Имя функции уведомления для `szExternalName`.  
  
 `vtPropType`  
 Значение, указывающее тип свойства.  
  
### <a name="remarks"></a>Примечания  
 В отличие от свойства, определенные с `DISP_PROPERTY`, свойство, определенное с `DISP_PROPERTY_NOTIFY` автоматически вызывает функции, указанной `pfnAfterSet` при изменении свойства.  
  
 `vtPropType` Аргумент имеет тип **VARTYPE**. Возможные значения для этого аргумента, взяты из `VARENUM` перечисления:  
  
|Символ|**Тип свойства**|  
|------------|-----------------------|  
|`VT_I2`|**short**|  
|`VT_I4`|**long**|  
|`VT_R4`|**float**|  
|`VT_R8`|**double**|  
|`VT_CY`|**CY**|  
|`VT_DATE`|**DATE**|  
|`VT_BSTR`|`CString`|  
|**VT_DISPATCH**|`LPDISPATCH`|  
|`VT_ERROR`|`SCODE`|  
|`VT_BOOL`|**BOOL**|  
|**VT_VARIANT**|**VARIANT**|  
|**VT_UNKNOWN**|`LPUNKNOWN`|  

### <a name="requirements"></a>Требования  
 **Заголовок:** afxdisp.h 

##  <a name="disp_property_param"></a>DISP_PROPERTY_PARAM  
 Определяет свойство с доступом с отдельными **получить** и `Set` функции-члены.  
  
```   
DISP_PROPERTY_PARAM(
  theClass, 
  pszExternalName, 
  pfnGet, 
  pfnSet, 
  vtPropType,
  vtsParams)   
```  
  
### <a name="parameters"></a>Параметры  
 `theClass`  
 Имя класса.  
  
 *pszExternalName*  
 Внешнее имя свойства.  
  
 `pfnGet`  
 Имя функции-члена, используемый для получения свойства.  
  
 `pfnSet`  
 Имя функции-члена, используемый для задания свойства.  
  
 `vtPropType`  
 Значение, указывающее тип свойства.  
  
 `vtsParams`  
 Строка разделенный пробелами **VTS_** типов variant параметра, один для каждого параметра.  
  
### <a name="remarks"></a>Примечания  
 В отличие от `DISP_PROPERTY_EX` макрос, этот макрос можно указать список параметров для свойства. Это полезно для реализации, параметризованные или индексированных свойств.  
  
### <a name="example"></a>Пример  
 Рассмотрим следующее объявление get и набора функций, которые позволяют пользователю запрашивать указанной строке и столбце при обращении к свойству:  
  
 [!code-cpp[NVC_MFCActiveXControl#9](../../mfc/codesnippet/cpp/dispatch-maps_3.h)]  
  
 Они соответствуют следующим `DISP_PROPERTY_PARAM` макрос в карте распределения элементов управления:  
  
 [!code-cpp[NVC_MFCActiveXControl#10](../../mfc/codesnippet/cpp/dispatch-maps_4.cpp)]  
  
 В качестве другого примера рассмотрим следующие get и набора функций:  
  
 [!code-cpp[NVC_MFCActiveXControl#11](../../mfc/codesnippet/cpp/dispatch-maps_5.h)]  
  
 Они соответствуют следующим `DISP_PROPERTY_PARAM` макрос в карте распределения элементов управления:  
  
 [!code-cpp[NVC_MFCActiveXControl#12](../../mfc/codesnippet/cpp/dispatch-maps_6.cpp)]  

### <a name="requirements"></a>Требования  
 **Заголовок:** afxdisp.h 

##  <a name="disp_defvalue"></a>DISP_DEFVALUE  
 Делает существующего свойства объекта, значение по умолчанию.  
  
```   
DISP_DEFVALUE(theClass, pszName)   
```  
  
### <a name="parameters"></a>Параметры  
 `theClass`  
 Имя класса.  
  
 `pszName`  
 Внешнее имя свойства, которое представляет объекта «значение».  
  
### <a name="remarks"></a>Примечания  
 Значение по умолчанию станет программирование объекта автоматизации проще для приложений Visual Basic.  
  
 «Default value» объект имеет свойство, получить или задать, когда ссылка на объект не указывает свойство или функции-члена.  

### <a name="requirements"></a>Требования  
 **Заголовок:** afxdisp.h 

## <a name="see-also"></a>См. также  
 [Макросы и глобальные объекты](../../mfc/reference/mfc-macros-and-globals.md)
