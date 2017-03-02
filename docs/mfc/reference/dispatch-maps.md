---
title: "Съемы | Документы Microsoft"
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
- dispatch maps. macros
- dispatch maps
- dispatch map macros
ms.assetid: bef9d08b-ad35-4c3a-99d8-04150c7c04e2
caps.latest.revision: 14
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
ms.openlocfilehash: 48e5d1fe207089733caa5ed9e8ca30c2de21f95f
ms.lasthandoff: 02/24/2017

---
# <a name="dispatch-maps"></a>Схемы подготовки к отправке
OLE-автоматизации предоставляет способы для вызова методов и доступа к свойствам в приложениях. Механизм, предоставляемые библиотеки классов Microsoft Foundation для диспетчеризации эти запросы — «диспетчеризации карта» представляет внутренние и внешние имена объекта функции и свойства, а также типы данных непосредственно из свойств и аргументов функции.  
  
### <a name="dispatch-maps"></a>Схемы подготовки к отправке  
  
|||  
|-|-|  
|[DECLARE_DISPATCH_MAP](#declare_dispatch_map)|Объявляет, что карта распределения будет использоваться для предоставления класса методы и свойства (необходимо использовать в объявлении класса).|  
|[BEGIN_DISPATCH_MAP](#begin_dispatch_map)|Начинается определение карту диспетчеризации.|  
|[END_DISPATCH_MAP](#end_dispatch_map)|Завершает определение карту диспетчеризации.|  
|[DISP_FUNCTION](#disp_function)|Используется в карте распределения для определения функции автоматизации OLE.|  
|[DISP_PROPERTY](#disp_property)|Определяет свойство автоматизации OLE.|  
|[DISP_PROPERTY_EX](#disp_property_ex)|Определяет свойство автоматизации OLE и имена функций Get и Set.|  
|[DISP_PROPERTY_NOTIFY](#disp_property_notify)|Определяет свойство автоматизации OLE с уведомлением.|  
|[DISP_PROPERTY_PARAM](#disp_property_param)|Определяет свойство автоматизации OLE, которая принимает параметры и имена функций Get и Set.|  
|[DISP_DEFVALUE](#disp_defvalue)|Делает существующее свойство объекта, значение по умолчанию.|  
  
##  <a name="a-namedeclaredispatchmapa--declaredispatchmap"></a><a name="declare_dispatch_map"></a>DECLARE_DISPATCH_MAP  
 Если `CCmdTarget`-производный класс в программе поддерживает OLE-автоматизации, что класс должен предоставлять карту диспетчеризации, чтобы предоставить его методы и свойства.  
  
```   
DECLARE_DISPATCH_MAP()  
```  
  
### <a name="remarks"></a>Примечания  
 Используйте `DECLARE_DISPATCH_MAP` макрос в конце объявления класса. Затем в. CPP-файл, который определяет член функции для класса, используйте `BEGIN_DISPATCH_MAP` макрос. Включите записи макроса для каждого класса представленной в методы и свойства ( `DISP_FUNCTION`, `DISP_PROPERTY`и так далее). Наконец, используйте `END_DISPATCH_MAP` макрос.  
  
> [!NOTE]
>  При объявлении элементов после `DECLARE_DISPATCH_MAP`, необходимо указать новый тип доступа ( **открытый**, `private`, или `protected`) для них.  
  
 Мастера приложений и кода мастера помогают в создании классов автоматизации и обслуживание схемы подготовки к отправке. Дополнительные сведения о картах диспетчеризации см [серверы автоматизации](../../mfc/automation-servers.md).  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCAutomation&#10;](../../mfc/codesnippet/cpp/dispatch-maps_1.h)]  

### <a name="requirements"></a>Требования  
 **Заголовок:** afxwin.h  

##  <a name="a-namebegindispatchmapa--begindispatchmap"></a><a name="begin_dispatch_map"></a>BEGIN_DISPATCH_MAP  
 Объявляет определение карту диспетчеризации.  
  
```  
BEGIN_DISPATCH_MAP(theClass, baseClass)   
```  
  
### <a name="parameters"></a>Параметры  
 `theClass`  
 Задает имя класса, который является владельцем этой карты распределения.  
  
 `baseClass`  
 Указывает имя базового класса `theClass`.  
  
### <a name="remarks"></a>Примечания  
 В файле реализации (CPP), который определяет функции-члены класса, запустите карту диспетчеризации с `BEGIN_DISPATCH_MAP` макрос, добавьте записи макроса для каждой функции отправки и свойств и завершения отправки карты с `END_DISPATCH_MAP` макрос.  

### <a name="requirements"></a>Требования  
 **Заголовок:** afxdisp.h  

##  <a name="a-nameenddispatchmapa--enddispatchmap"></a><a name="end_dispatch_map"></a>END_DISPATCH_MAP  
 Завершает определение карту диспетчеризации.  
  
```   
END_DISPATCH_MAP()  
```  
  
### <a name="remarks"></a>Примечания  
 Он должен использоваться в сочетании с `BEGIN_DISPATCH_MAP`.  

### <a name="requirements"></a>Требования  
 **Заголовок:** afxdisp.h  

##  <a name="a-namedispfunctiona--dispfunction"></a><a name="disp_function"></a>DISP_FUNCTION  
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
 Значение, указывающее тип возвращаемого функцией значения.  
  
 `vtsParams`  
 Разделенный пробелами список из одной или нескольких констант, указав список параметров функции.  
  
### <a name="remarks"></a>Примечания  
 `vtRetVal` Аргумент имеет тип **VARTYPE**. Следующие возможные значения для этого аргумента взяты из `VARENUM` перечисления:  
  
|Символ|Тип возвращаемого значения|  
|------------|-----------------|  
|`VT_EMPTY`|`void`|  
|`VT_I2`|**short**|  
|`VT_I4`|**long**|  
|`VT_R4`|**float**|  
|`VT_R8`|**double**|  
|`VT_CY`|**ПОЛУГОДИЕ**|  
|`VT_DATE`|**ДАТА**|  
|`VT_BSTR`|`BSTR`|  
|**VT_DISPATCH**|`LPDISPATCH`|  
|`VT_ERROR`|`SCODE`|  
|`VT_BOOL`|**BOOL**|  
|**VT_VARIANT**|**VARIANT**|  
|**VT_UNKNOWN**|`LPUNKNOWN`|  
  
 `vtsParams` Аргумент является разделенный пробелами список значений из **VTS_** константы. Один или несколько из этих значений, разделенных пробелами (не запятые) Указывает список параметров функции. Например: 
  
 [!code-cpp[NVC_MFCAutomation&#14;](../../mfc/codesnippet/cpp/dispatch-maps_2.cpp)]  
  
 Указывает список, содержащий короткое целое число, следуют указатель короткое целое число со знаком.  
  
 **VTS_** константы имеют следующим образом:  
  
|Символ|Тип параметра|  
|------------|--------------------|  
|**VTS_I2**|`Short`|  
|**VTS_I4**|`Long`|  
|**VTS_R4**|**Число с плавающей запятой**|  
|**VTS_R8**|`Double`|  
|**VTS_CY**|**const CY** или **кг\***|  
|**VTS_DATE**|**ДАТА**|  
|**VTS_BSTR**|`LPCSTR`|  
|**VTS_DISPATCH**|`LPDISPATCH`|  
|**VTS_SCODE**|`SCODE`|  
|**VTS_BOOL**|**BOOL**|  
|**VTS_VARIANT**|**const ВАРИАНТ\* ** или **VARIANT &**|  
|**VTS_UNKNOWN**|`LPUNKNOWN`|  
|**VTS_PI2**|**короткий\***|  
|**VTS_PI4**|**длинное\***|  
|**VTS_PR4**|**число с плавающей запятой\***|  
|**VTS_PR8**|**Double\***|  
|**VTS_PCY**|**ПОЛУГОДИЕ\***|  
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

##  <a name="a-namedisppropertya--dispproperty"></a><a name="disp_property"></a>DISP_PROPERTY  
 Определяет свойство автоматизации OLE в карту диспетчеризации.  
  
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
 `vtPropType` Аргумент имеет тип **VARTYPE**. Возможные значения для этого аргумента взяты из `VARENUM` перечисления:  
  
|Символ|**Тип свойства**|  
|------------|-----------------------|  
|`VT_I2`|**short**|  
|`VT_I4`|**long**|  
|`VT_R4`|**float**|  
|`VT_R8`|**double**|  
|`VT_CY`|**ПОЛУГОДИЕ**|  
|`VT_DATE`|**ДАТА**|  
|`VT_BSTR`|`CString`|  
|**VT_DISPATCH**|`LPDISPATCH`|  
|`VT_ERROR`|`SCODE`|  
|`VT_BOOL`|**BOOL**|  
|**VT_VARIANT**|**VARIANT**|  
|**VT_UNKNOWN**|`LPUNKNOWN`|  
  
 Изменения свойства, значение переменной-члена, определяемое внешнего клиента `memberName` изменяет; нет уведомлений об изменении.  

### <a name="requirements"></a>Требования  
 **Заголовок:** afxdisp.h 

##  <a name="a-namedisppropertyexa--disppropertyex"></a><a name="disp_property_ex"></a>DISP_PROPERTY_EX  
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
 Имя функции-члена используется для получения свойства.  
  
 `memberSet`  
 Имя функции-члена используется для задания свойства.  
  
 `vtPropType`  
 Значение, указывающее тип свойства.  
  
### <a name="remarks"></a>Примечания  
 `memberGet` И `memberSet` функции имеют подписи определяется `vtPropType` аргумент. `memberGet` Функция не принимает аргументы и возвращает значение типа, указанного параметром `vtPropType`. `memberSet` Функция принимает аргумент типа, указанного в `vtPropType` и не возвращает ничего.  
  
 `vtPropType` Аргумент имеет тип **VARTYPE**. Возможные значения для этого аргумента взяты из `VARENUM` перечисления. Список этих значений см `vtRetVal` параметр в [DISP_FUNCTION](#disp_function). Обратите внимание, что `VT_EMPTY`, перечисленных в `DISP_FUNCTION` примечания, запрещается использовать как тип данных свойства.  

### <a name="requirements"></a>Требования  
 **Заголовок:** afxdisp.h 

##  <a name="a-namedisppropertynotifya--disppropertynotify"></a><a name="disp_property_notify"></a>DISP_PROPERTY_NOTIFY  
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
 В отличие от свойства, определяемые `DISP_PROPERTY`, свойство, определенное с `DISP_PROPERTY_NOTIFY` будет автоматически вызывать функции, указанной `pfnAfterSet` при изменении свойства.  
  
 `vtPropType` Аргумент имеет тип **VARTYPE**. Возможные значения для этого аргумента взяты из `VARENUM` перечисления:  
  
|Символ|**Тип свойства**|  
|------------|-----------------------|  
|`VT_I2`|**short**|  
|`VT_I4`|**long**|  
|`VT_R4`|**float**|  
|`VT_R8`|**double**|  
|`VT_CY`|**ПОЛУГОДИЕ**|  
|`VT_DATE`|**ДАТА**|  
|`VT_BSTR`|`CString`|  
|**VT_DISPATCH**|`LPDISPATCH`|  
|`VT_ERROR`|`SCODE`|  
|`VT_BOOL`|**BOOL**|  
|**VT_VARIANT**|**VARIANT**|  
|**VT_UNKNOWN**|`LPUNKNOWN`|  

### <a name="requirements"></a>Требования  
 **Заголовок:** afxdisp.h 

##  <a name="a-namedisppropertyparama--disppropertyparam"></a><a name="disp_property_param"></a>DISP_PROPERTY_PARAM  
 Определяет свойство, доступ с помощью отдельных **получить** и `Set` функции-члены.  
  
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
 Имя функции-члена используется для получения свойства.  
  
 `pfnSet`  
 Имя функции-члена используется для задания свойства.  
  
 `vtPropType`  
 Значение, указывающее тип свойства.  
  
 `vtsParams`  
 Строка разделенных запятыми **VTS_** типов variant параметра, один для каждого параметра.  
  
### <a name="remarks"></a>Примечания  
 В отличие от `DISP_PROPERTY_EX` макрос, этот макрос можно указать список параметров для свойства. Это полезно для реализации, индексирование или параметризованные свойства.  
  
### <a name="example"></a>Пример  
 Рассмотрим следующее объявление get и набора функций, которые позволяют пользователю для запроса конкретных строк и столбцов при доступе к свойству:  
  
 [!code-cpp[NVC_MFCActiveXControl №&9;](../../mfc/codesnippet/cpp/dispatch-maps_3.h)]  
  
 Эти значения соответствуют следующим `DISP_PROPERTY_PARAM` макрос в карте распределения элементов управления:  
  
 [!code-cpp[NVC_MFCActiveXControl&#10;](../../mfc/codesnippet/cpp/dispatch-maps_4.cpp)]  
  
 В качестве другого примера рассмотрим следующие get и набора функций:  
  
 [!code-cpp[NVC_MFCActiveXControl&11;](../../mfc/codesnippet/cpp/dispatch-maps_5.h)]  
  
 Эти значения соответствуют следующим `DISP_PROPERTY_PARAM` макрос в карте распределения элементов управления:  
  
 [!code-cpp[NVC_MFCActiveXControl&#12;](../../mfc/codesnippet/cpp/dispatch-maps_6.cpp)]  

### <a name="requirements"></a>Требования  
 **Заголовок:** afxdisp.h 

##  <a name="a-namedispdefvaluea--dispdefvalue"></a><a name="disp_defvalue"></a>DISP_DEFVALUE  
 Делает существующее свойство объекта, значение по умолчанию.  
  
```   
DISP_DEFVALUE(theClass, pszName)   
```  
  
### <a name="parameters"></a>Параметры  
 `theClass`  
 Имя класса.  
  
 `pszName`  
 Внешнее имя свойство, представляющее объекта «значение».  
  
### <a name="remarks"></a>Примечания  
 Значения по умолчанию можно сделать программирование объекта автоматизации проще для приложений Visual Basic.  
  
 «Значение по умолчанию» объекта — свойство, получить или задать, когда ссылка на объект не указывает свойство или функции-члена.  

### <a name="requirements"></a>Требования  
 **Заголовок:** afxdisp.h 

## <a name="see-also"></a>См. также  
 [Макросы и глобальные объекты](../../mfc/reference/mfc-macros-and-globals.md)

