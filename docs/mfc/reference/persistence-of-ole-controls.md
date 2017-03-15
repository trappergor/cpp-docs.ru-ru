---
title: "Сохраняемость элементов управления OLE | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vc.mfc.macros.ole
dev_langs:
- C++
helpviewer_keywords:
- OLE controls, persistence
- persistence, OLE controls
ms.assetid: 64f8dc80-f110-41af-b3ea-14948f6bfdf7
caps.latest.revision: 17
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
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: b8bbf72a1ea16b37dabf88c5d41a34b1a03ba0d1
ms.lasthandoff: 02/24/2017

---
# <a name="persistence-of-ole-controls"></a>Сохраняемость элементов управления OLE
Одна из возможностей элементов управления OLE является свойство сохранения (или сериализации), который позволяет элементу управления OLE для чтения или записи значения свойств в и из файла или потока. Приложение контейнера можно использовать сериализацию для хранения значений свойств элемента управления, даже в том случае, если приложение уничтожила элемента управления. Значения свойств элемента управления OLE могут считываться из файла или потока при создании нового экземпляра элемента управления создается на более позднее время.  
  
### <a name="persistence-of-ole-controls"></a>Сохраняемость элементов управления OLE  
  
|||  
|-|-|  
|[PX_Blob](#px_blob)|Меняет местами свойства элемента управления, который сохраняет данные больших двоичных объектов (BLOB).|  
|[PX_Bool](#px_bool)|Меняет местами свойства элемента управления типа **BOOL**.|  
|[PX_Color](#px_color)|Меняет местами свойство цвет элемента управления.|  
|[PX_Currency](#px_currency)|Меняет местами свойства элемента управления типа **CY**.|  
|[PX_DataPath](#px_datapath)|Меняет местами свойства элемента управления типа `CDataPathProperty`.|  
|[PX_Double](#px_double)|Меняет местами свойства элемента управления типа **двойные**.|  
|[PX_Font](#px_font)|Меняет местами свойства шрифта элемента управления.|  
|[PX_Float](#px_float)|Меняет местами свойства элемента управления типа **float**.|  
|[PX_IUnknown](#px_iunknown)|Меняет местами свойства элемента управления неопределенного типа.|  
|[PX_Long](#px_long)|Меняет местами свойства элемента управления типа **длинные**.|  
|[PX_Picture](#px_picture)|Меняет местами рисунок свойство элемента управления.|  
|[PX_Short](#px_short)|Меняет местами свойства элемента управления типа **короткие**.|  
|[PX_ULong](#px_ulong)|Меняет местами свойства элемента управления типа **ULONG**.|  
|[PX_UShort](#px_ushort)|Меняет местами свойства элемента управления типа **USHORT**.|  
|[PXstring](#px_string)|Меняет местами символ строковое свойство элемента управления.|  
|[PX_VBXFontConvert](#px_vbxfontconvert)|Меняет местами свойства, связанные со шрифтами VBX элемента управления в свойстве шрифта элемента управления OLE.|  
  
 Кроме того `AfxOleTypeMatchGuid` глобальная функция предоставляется для проверки на соответствие между `TYPEDESC` и с указанным кодом GUID.  
  
##  <a name="a-namepxbloba--pxblob"></a><a name="px_blob"></a>PX_Blob  
 Эта функция внутри элемента управления `DoPropExchange` функции-члена для сериализации или инициализировать свойство, которое хранит данные больших двоичных объектов (BLOB).  
  
```  
 
BOOL  
PX_Blob(
    CPropExchange* 
pPX  ,  
    LPCTSTR 
pszPropName  ,  
    HGLOBAL& 
hBlob  ,  
    HGLOBAL 
hBlobDefault  
= NULL);  
```  
  
### <a name="parameters"></a>Параметры  
 `pPX`  
 Указатель на [CPropExchange](../../mfc/reference/cpropexchange-class.md) объекта (обычно передается в качестве параметра `DoPropExchange`).  
  
 `pszPropName`  
 Имя свойства при обмене.  
  
 `hBlob`  
 Ссылка на переменную, где хранятся свойства (обычно переменную-член класса).  
  
 `hBlobDefault`  
 Значение по умолчанию для свойства.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если exchange был успешным; 0, если операция завершилась неудачей.  
  
### <a name="remarks"></a>Примечания  
 Значение свойства будет считывать или записью в переменную ссылается `hBlob`соответствующим образом. Этой переменной должен быть инициализирован для **NULL** перед вызовом изначально `PX_Blob` в первый раз (как правило, это можно сделать в конструкторе элемента управления). Если `hBlobDefault` указан, будет использоваться как значение свойства по умолчанию. Это значение используется в том случае, если по какой-либо причине происходит сбой процесса инициализации или сериализации элемента управления.  
  
 Дескрипторы `hBlob` и `hBlobDefault` ссылки на блок памяти, который содержит следующее:  
  
-   Объект `DWORD` , содержащее длину в байтах, двоичных данных, следующим за немедленно  
  
-   Блок памяти, содержащий двоичные данные.  
  
 Обратите внимание, что `PX_Blob` приведет к выделению памяти, с помощью Windows [GlobalAlloc](http://msdn.microsoft.com/library/windows/desktop/aa366574) API, при загрузке свойств типа BLOB. Вы несете ответственность за освобождение памяти. Таким образом, деструктор элемент управления должен вызывать [GlobalFree](http://msdn.microsoft.com/library/windows/desktop/aa366579) для любого свойства типа BLOB дескрипторы для освобождения вверх память, выделенную для элемента управления.  
  
##  <a name="a-namepxboola--pxbool"></a><a name="px_bool"></a>PX_Bool  
 Эта функция внутри элемента управления `DoPropExchange` функции-члена для сериализации или инициализировать свойство типа **BOOL**.  
  
```  
 
BOOL  
PX_Bool(
    CPropExchange* 
pPX  ,  
    LPCTSTR 
pszPropName  ,  
    BOOL& bValue);

BOOL  
PX_Bool(
    CPropExchange* 
pPX  ,  
    LPCTSTR 
pszPropName  ,  
    BOOL& 
bValue  ,  
    BOOL bDefault);  
```  
  
### <a name="parameters"></a>Параметры  
 `pPX`  
 Указатель на [CPropExchange](../../mfc/reference/cpropexchange-class.md) объекта (обычно передается в качестве параметра `DoPropExchange`).  
  
 `pszPropName`  
 Имя свойства при обмене.  
  
 `bValue`  
 Ссылка на переменную, где хранятся свойства (обычно переменную-член класса).  
  
 `bDefault`  
 Значение по умолчанию для свойства.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если exchange был успешным; 0, если операция завершилась неудачей.  
  
### <a name="remarks"></a>Примечания  
 Значение свойства будет считывать или записью в переменную ссылается `bValue`соответствующим образом. Если `bDefault` указан, будет использоваться как значение свойства по умолчанию. Это значение используется в том случае, если по какой-либо причине происходит сбой элемента управления процессом сериализации.  
  
##  <a name="a-namepxcolora--pxcolor"></a><a name="px_color"></a>PX_Color  
 Эта функция внутри элемента управления `DoPropExchange` функции-члена для сериализации или инициализировать свойство типа **OLE_COLOR**.  
  
```  
 
BOOL PX_Color(
    CPropExchange* 
pPX  ,  
    LPCTSTR 
pszPropName  ,  
    OLE_COLOR& clrValue);

BOOL PX_Color(
    CPropExchange* 
pPX  ,  
    LPCTSTR 
pszPropName  ,  
    OLE_COLOR& 
clrValue  ,  
    OLE_COLOR 
clrDefault);  
```  
  
### <a name="parameters"></a>Параметры  
 `pPX`  
 Указатель на [CPropExchange](../../mfc/reference/cpropexchange-class.md) объекта (обычно передается в качестве параметра `DoPropExchange`).  
  
 `pszPropName`  
 Имя свойства при обмене.  
  
 `clrValue`  
 Ссылка на переменную, где хранятся свойства (обычно переменную-член класса).  
  
 `clrDefault`  
 Значение по умолчанию для свойства, определяемые разработчиком элемента управления.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если exchange был успешным; 0, если операция завершилась неудачей.  
  
### <a name="remarks"></a>Примечания  
 Значение свойства будет считывать или записью в переменную ссылается `clrValue`соответствующим образом. Если `clrDefault` указан, будет использоваться как значение свойства по умолчанию. Это значение используется в том случае, если по какой-либо причине происходит сбой элемента управления процессом сериализации.  
  
##  <a name="a-namepxcurrencya--pxcurrency"></a><a name="px_currency"></a>PX_Currency  
 Эта функция внутри элемента управления `DoPropExchange` функции-члена для сериализации или инициализировать свойство типа **валюты**.  
  
```  
 
BOOL  
PX_Currency(
    CPropExchange* 
pPX  ,  
    LPCTSTR 
pszPropName  ,  
    CY& cyValue);

BOOL  
PX_Currency(
    CPropExchange* 
pPX  ,  
    LPCTSTR 
pszPropName  ,  
    CY& 
cyValue  ,  
    CY cyDefault);  
```  
  
### <a name="parameters"></a>Параметры  
 `pPX`  
 Указатель на [CPropExchange](../../mfc/reference/cpropexchange-class.md) объекта (обычно передается в качестве параметра `DoPropExchange`).  
  
 `pszPropName`  
 Имя свойства при обмене.  
  
 `cyValue`  
 Ссылка на переменную, где хранятся свойства (обычно переменную-член класса).  
  
 `cyDefault`  
 Значение по умолчанию для свойства.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если exchange был успешным; 0, если операция завершилась неудачей.  
  
### <a name="remarks"></a>Примечания  
 Значение свойства будет считывать или записью в переменную ссылается `cyValue`соответствующим образом. Если `cyDefault` указан, будет использоваться как значение свойства по умолчанию. Это значение используется в том случае, если по какой-либо причине происходит сбой элемента управления процессом сериализации.  
  
##  <a name="a-namepxdatapatha--pxdatapath"></a><a name="px_datapath"></a>PX_DataPath  
 Эта функция внутри элемента управления `DoPropExchange` функции-члена для сериализации или инициализировать свойство типа данных пути [CDataPathProperty](../../mfc/reference/cdatapathproperty-class.md).  
  
```  
 
BOOL  
PX_DataPath(
    CPropExchange* 
pPX,  
    LPCTSTR 
pszPropName,  
    CDataPathProperty& dataPathProperty);

BOOL  
PX_DataPath(
    CPropExchange* 
pPX,  
    CDataPathProperty& dataPathProperty);  
```  
  
### <a name="parameters"></a>Параметры  
 `pPX`  
 Указатель на [CPropExchange](../../mfc/reference/cpropexchange-class.md) объекта (обычно передается в качестве параметра `DoPropExchange`).  
  
 `pszPropName`  
 Имя свойства при обмене.  
  
 `dataPathProperty`  
 Ссылка на переменную, где хранятся свойства (обычно переменную-член класса).  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если exchange был успешным; 0, если операция завершилась неудачей.  
  
### <a name="remarks"></a>Примечания  
 Свойства пути данных реализовать асинхронный элемент управления свойства. Значение свойства будет считывать или записью в переменную ссылается `dataPathProperty`соответствующим образом.  
  
##  <a name="a-namepxdoublea--pxdouble"></a><a name="px_double"></a>PX_Double  
 Эта функция внутри элемента управления `DoPropExchange` функции-члена для сериализации или инициализировать свойство типа **двойные**.  
  
```  
 
BOOL  
PX_Double(
    CPropExchange* 
pPX  ,  
    LPCTSTR 
pszPropName  ,  
    double& doubleValue);

BOOL  
PX_Double(
    CPropExchange* 
pPX  ,  
    LPCTSTR 
pszPropName  ,  
    double& 
doubleValue  ,  
    double doubleDefault);  
```  
  
### <a name="parameters"></a>Параметры  
 `pPX`  
 Указатель на [CPropExchange](../../mfc/reference/cpropexchange-class.md) объекта (обычно передается в качестве параметра `DoPropExchange`).  
  
 `pszPropName`  
 Имя свойства при обмене.  
  
 `doubleValue`  
 Ссылка на переменную, где хранятся свойства (обычно переменную-член класса).  
  
 `doubleDefault`  
 Значение по умолчанию для свойства.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если exchange был успешным; 0, если операция завершилась неудачей.  
  
### <a name="remarks"></a>Примечания  
 Значение свойства чтение и запись в переменную ссылается `doubleValue`соответствующим образом. Если `doubleDefault` указан, будет использоваться как значение свойства по умолчанию. Это значение используется в том случае, если по какой-либо причине происходит сбой элемента управления процессом сериализации.  
  
##  <a name="a-namepxfonta--pxfont"></a><a name="px_font"></a>PX_Font  
 Эта функция внутри элемента управления `DoPropExchange` функции-члена для сериализации или инициализировать свойство типа шрифта.  
  
```  
 
BOOL  
PX_Font(
    CPropExchange* 
pPX  ,  
    LPCTSTR 
pszPropName  ,  
    CFontHolder& 
font  ,  
    const 
FONTDESC  
FAR* 
pFontDesc  
= 
NULL,  
    LPFONTDISP 
pFontDispAmbient  
= NULL);  
```  
  
### <a name="parameters"></a>Параметры  
 `pPX`  
 Указатель на [CPropExchange](../../mfc/reference/cpropexchange-class.md) объекта (обычно передается в качестве параметра `DoPropExchange`).  
  
 `pszPropName`  
 Имя свойства при обмене.  
  
 `font`  
 Ссылку на `CFontHolder` , содержащий свойства шрифта.  
  
 `pFontDesc`  
 Указатель на **FONTDESC** структура, содержащая значения, используемые в состояние по умолчанию для свойства шрифта, в случае инициализации где `pFontDispAmbient` — **NULL**.  
  
 `pFontDispAmbient`  
 Указатель на **IFontDisp** интерфейс шрифт, используемый при инициализации состояния по умолчанию этого свойства шрифта.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если exchange был успешным; 0, если операция завершилась неудачей.  
  
### <a name="remarks"></a>Примечания  
 Значение свойства чтение и запись для `font`, `CFontHolder` ссылку, при необходимости. Если `pFontDesc` и `pFontDispAmbient` указаны, они используются для инициализации значения этого свойства по умолчанию, при необходимости. Эти значения используются в том случае, если по какой-либо причине происходит сбой элемента управления процессом сериализации. Как правило, передайте **NULL** для `pFontDesc` и окружающей среды значение, возвращаемое `COleControl::AmbientFont` для `pFontDispAmbient`. Обратите внимание, что возвращаемый объект шрифта `COleControl::AmbientFont` должны быть освобождены с помощью вызова **IFontDisp::Release** функции-члена.  
  
##  <a name="a-namepxfloata--pxfloat"></a><a name="px_float"></a>PX_Float  
 Эта функция внутри элемента управления `DoPropExchange` функции-члена для сериализации или инициализировать свойство типа **float**.  
  
```  
 
BOOL  
PX_Float(
    CPropExchange* 
pPX  ,  
    LPCTSTR 
pszPropName  ,  
    float& floatValue);

BOOL  
PX_Float(
    CPropExchange* 
pPX  ,  
    LPCTSTR 
pszPropName  ,  
    float& 
floatValue  ,  
    float floatDefault);  
```  
  
### <a name="parameters"></a>Параметры  
 `pPX`  
 Указатель на [CPropExchange](../../mfc/reference/cpropexchange-class.md) объекта (обычно передается в качестве параметра `DoPropExchange`).  
  
 `pszPropName`  
 Имя свойства при обмене.  
  
 `floatValue`  
 Ссылка на переменную, где хранятся свойства (обычно переменную-член класса).  
  
 `floatDefault`  
 Значение по умолчанию для свойства.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если exchange был успешным; 0, если операция завершилась неудачей.  
  
### <a name="remarks"></a>Примечания  
 Значение свойства чтение и запись в переменную ссылается `floatValue`соответствующим образом. Если `floatDefault` указан, будет использоваться как значение свойства по умолчанию. Это значение используется в том случае, если по какой-либо причине происходит сбой элемента управления процессом сериализации.  
  
##  <a name="a-namepxiunknowna--pxiunknown"></a><a name="px_iunknown"></a>PX_IUnknown  
 Эта функция внутри элемента управления `DoPropExchange` функции-члена для сериализации или инициализировать представлены, у которых свойство **IUnknown**-производный интерфейс.  
  
```  
 
BOOL  
PX_IUnknown(
    CPropExchange* 
pPX  ,  
    LPCTSTR 
pszPropName  ,  
    LPUNKNOWN& 
pUnk  ,  
    REFIID 
iid  ,  
    LPUNKNOWN 
pUnkDefault  
= NULL);  
```  
  
### <a name="parameters"></a>Параметры  
 `pPX`  
 Указатель на [CPropExchange](../../mfc/reference/cpropexchange-class.md) объекта (обычно передается в качестве параметра `DoPropExchange`).  
  
 `pszPropName`  
 Имя свойства при обмене.  
  
 *pUnk*  
 Ссылка на переменную, содержащую интерфейс объект, представляющий значение свойства.  
  
 `iid`  
 Идентификатор интерфейса, указывающий, какой интерфейс объект свойства, используемые элементом управления.  
  
 `pUnkDefault`  
 Значение по умолчанию для свойства.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если exchange был успешным; 0, если операция завершилась неудачей.  
  
### <a name="remarks"></a>Примечания  
 Значение свойства чтение и запись в переменную ссылается *pUnk*соответствующим образом. Если `pUnkDefault` указан, будет использоваться как значение свойства по умолчанию. Это значение используется в том случае, если по какой-либо причине происходит сбой элемента управления процессом сериализации.  
  
##  <a name="a-namepxlonga--pxlong"></a><a name="px_long"></a>PX_Long  
 Эта функция внутри элемента управления `DoPropExchange` функции-члена для сериализации или инициализировать свойство типа **длинные**.  
  
```  
 
BOOL  
PX_Long(
    CPropExchange* 
pPX  ,  
    LPCTSTR 
pszPropName  ,  
    long& lValue);

BOOL  
PX_Long(
    CPropExchange* 
pPX  ,  
    LPCTSTR 
pszPropName  ,  
    long& 
lValue  ,  
    long lDefault);  
```  
  
### <a name="parameters"></a>Параметры  
 `pPX`  
 Указатель на [CPropExchange](../../mfc/reference/cpropexchange-class.md) объекта (обычно передается в качестве параметра `DoPropExchange`).  
  
 `pszPropName`  
 Имя свойства при обмене.  
  
 `lValue`  
 Ссылка на переменную, где хранятся свойства (обычно переменную-член класса).  
  
 `lDefault`  
 Значение по умолчанию для свойства.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если exchange был успешным; 0, если операция завершилась неудачей.  
  
### <a name="remarks"></a>Примечания  
 Значение свойства чтение и запись в переменную ссылается `lValue`соответствующим образом. Если `lDefault` указан, будет использоваться как значение свойства по умолчанию. Это значение используется в том случае, если по какой-либо причине происходит сбой элемента управления процессом сериализации.  
  
##  <a name="a-namepxpicturea--pxpicture"></a><a name="px_picture"></a>PX_Picture  
 Эта функция внутри элемента управления `DoPropExchange` функции-члена для сериализации или инициализировать свойство изображения элемента управления.  
  
```  
 
BOOL  
PX_Picture(
    CPropExchange* 
pPX  ,  
    LPCTSTR 
pszPropName  ,  
    CPictureHolder& pict);

BOOL  
PX_Picture(
    CPropExchange* 
pPX  ,  
    LPCTSTR 
pszPropName  ,  
    CPictureHolder& 
pict  ,  
    CPictureHolder& pictDefault);  
```  
  
### <a name="parameters"></a>Параметры  
 `pPX`  
 Указатель на [CPropExchange](../../mfc/reference/cpropexchange-class.md) объекта (обычно передается в качестве параметра `DoPropExchange`).  
  
 `pszPropName`  
 Имя свойства при обмене.  
  
 `pict`  
 Ссылка на [CPictureHolder](../../mfc/reference/cpictureholder-class.md) объекта, где хранятся свойства (обычно переменную-член класса).  
  
 `pictDefault`  
 Значение по умолчанию для свойства.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если exchange был успешным; 0, если операция завершилась неудачей.  
  
### <a name="remarks"></a>Примечания  
 Значение свойства чтение и запись в переменную ссылается `pict`соответствующим образом. Если `pictDefault` указан, будет использоваться как значение свойства по умолчанию. Это значение используется в том случае, если по какой-либо причине происходит сбой элемента управления процессом сериализации.  
  
##  <a name="a-namepxshorta--pxshort"></a><a name="px_short"></a>PX_Short  
 Эта функция внутри элемента управления `DoPropExchange` функции-члена для сериализации или инициализировать свойство типа **короткие**.  
  
```  
 
BOOL  
PX_Short(
    CPropExchange* 
pPX  ,  
    LPCTSTR 
pszPropName  ,  
    short& sValue);

BOOL  
PX_Short(
    CPropExchange* 
pPX  ,  
    LPCTSTR 
pszPropName  ,  
    short& 
sValue  ,  
    short sDefault);  
```  
  
### <a name="parameters"></a>Параметры  
 `pPX`  
 Указатель на [CPropExchange](../../mfc/reference/cpropexchange-class.md) объекта (обычно передается в качестве параметра `DoPropExchange`).  
  
 `pszPropName`  
 Имя свойства при обмене.  
  
 `sValue`  
 Ссылка на переменную, где хранятся свойства (обычно переменную-член класса).  
  
 `sDefault`  
 Значение по умолчанию для свойства.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если exchange был успешным; 0, если операция завершилась неудачей.  
  
### <a name="remarks"></a>Примечания  
 Значение свойства чтение и запись в переменную ссылается `sValue`соответствующим образом. Если `sDefault` указан, будет использоваться как значение свойства по умолчанию. Это значение используется в том случае, если по какой-либо причине происходит сбой элемента управления процессом сериализации.  
  
##  <a name="a-namepxulonga--pxulong"></a><a name="px_ulong"></a>PX_ULong  
 Эта функция внутри элемента управления `DoPropExchange` функции-члена для сериализации или инициализировать свойство типа **ULONG**.  
  
```  
 
BOOL  
PX_ULong(
    CPropExchange* 
pPX  ,  
    LPCTSTR 
pszPropName  ,  
    ULONG& ulValue);

BOOL  
PX_ULong(
    CPropExchange* 
pPX  ,  
    LPCTSTR 
pszPropName  ,  
    ULONG& 
ulValue  ,  
    long ulDefault);  
```  
  
### <a name="parameters"></a>Параметры  
 `pPX`  
 Указатель на [CPropExchange](../../mfc/reference/cpropexchange-class.md) объекта (обычно передается в качестве параметра `DoPropExchange`).  
  
 `pszPropName`  
 Имя свойства при обмене.  
  
 `ulValue`  
 Ссылка на переменную, где хранятся свойства (обычно переменную-член класса).  
  
 `ulDefault`  
 Значение по умолчанию для свойства.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если exchange был успешным; 0, если операция завершилась неудачей.  
  
### <a name="remarks"></a>Примечания  
 Значение свойства чтение и запись в переменную ссылается `ulValue`соответствующим образом. Если `ulDefault` указан, будет использоваться как значение свойства по умолчанию. Это значение используется в том случае, если по какой-либо причине происходит сбой элемента управления процессом сериализации.  
  
##  <a name="a-namepxushorta--pxushort"></a><a name="px_ushort"></a>PX_UShort  
 Эта функция внутри элемента управления `DoPropExchange` функции-члена для сериализации или инициализировать свойство типа `unsigned` **короткие**.  
  
```  
 
BOOL  
PX_UShort(
    CPropExchange* 
pPX  ,  
    LPCTSTR 
pszPropName  ,  
    USHORT& usValue);

BOOL  
PX_UShort(
    CPropExchange* 
pPX  ,  
    LPCTSTR 
pszPropName  ,  
    USHORT& 
usValue  ,  
    USHORT usDefault);  
```  
  
### <a name="parameters"></a>Параметры  
 `pPX`  
 Указатель на [CPropExchange](../../mfc/reference/cpropexchange-class.md) объекта (обычно передается в качестве параметра `DoPropExchange`).  
  
 `pszPropName`  
 Имя свойства при обмене.  
  
 *usValue*  
 Ссылка на переменную, где хранятся свойства (обычно переменную-член класса).  
  
 *usDefault*  
 Значение по умолчанию для свойства.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если exchange был успешным; 0, если операция завершилась неудачей.  
  
### <a name="remarks"></a>Примечания  
 Значение свойства чтение и запись в переменную ссылается *usValue*соответствующим образом. Если *usDefault* указан, будет использоваться как значение свойства по умолчанию. Это значение используется в том случае, если по какой-либо причине происходит сбой элемента управления процессом сериализации.  
  
##  <a name="a-namepxstringa--pxstring"></a><a name="px_string"></a>PXstring  
 Эта функция внутри элемента управления **DoPropExchange** функции-члена для сериализации или инициализировать свойство строки символов.  
  
```  
 
BOOL  
PXstring(
    CPropExchange* 
pPX  ,  
    LPCTSTR 
pszPropName  ,  
    CString& strValue);

BOOL  
PXstring(
    CPropExchange* 
pPX  ,  
    LPCTSTR 
pszPropName  ,  
    CString& 
strValue  ,  
    CString strDefault);  
```  
  
### <a name="parameters"></a>Параметры  
 `pPX`  
 Указатель на [CPropExchange](../../mfc/reference/cpropexchange-class.md) объекта (обычно передается в качестве параметра `DoPropExchange`).  
  
 `pszPropName`  
 Имя свойства при обмене.  
  
 `strValue`  
 Ссылка на переменную, где хранятся свойства (обычно переменную-член класса).  
  
 `strDefault`  
 Значение по умолчанию для свойства.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если exchange был успешным; 0, если операция завершилась неудачей.  
  
### <a name="remarks"></a>Примечания  
 Значение свойства чтение и запись в переменную ссылается `strValue`соответствующим образом. Если `strDefault` указан, будет использоваться как значение свойства по умолчанию. Это значение используется в том случае, если по какой-либо причине происходит сбой элемента управления процессом сериализации.  
  
##  <a name="a-namepxvbxfontconverta--pxvbxfontconvert"></a><a name="px_vbxfontconvert"></a>PX_VBXFontConvert  
 Эта функция внутри элемента управления `DoPropExchange` функции-члена для инициализации свойства шрифта путем преобразования свойств шрифте VBX элемента управления.  
  
```  
 
BOOL  
PX_VBXFontConvert(
    CPropExchange* 
pPX  ,  
    CFontHolder& font);  
```  
  
### <a name="parameters"></a>Параметры  
 `pPX`  
 Указатель на [CPropExchange](../../mfc/reference/cpropexchange-class.md) объекта (обычно передается в качестве параметра `DoPropExchange`).  
  
 `font`  
 Свойства шрифта элемента управления OLE, который будет содержать преобразованные свойства VBX шрифте.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если exchange был успешным; 0, если операция завершилась неудачей.  
  
### <a name="remarks"></a>Примечания  
 Эта функция должна использоваться только элемента управления OLE, предназначенный для прямого управления VBX замены. Если среда разработки Visual Basic преобразует форму, содержащую элемент управления VBX для использования соответствующего замены элементов управления OLE, он будет вызывать элемент управления **IDataObject::SetData** функцию, передавая набор свойств, содержащий данные элемента управления VBX свойства. Эта операция, в свою очередь, вызывает элемент управления `DoPropExchange` вызываемая функция. `DoPropExchange`можно вызвать `PX_VBXFontConvert` для преобразования свойств, относящихся к шрифту VBX элемента управления (например, «FontName,» «Размер шрифта», и так далее) на соответствующие компоненты свойства шрифта элемента управления OLE.  
  
 `PX_VBXFontConvert`должен вызываться только после элемента управления на самом деле преобразуется из приложения VBX формы. Пример:  
  
 [!code-cpp[NVC_MFCActiveXControl&#14;](../../mfc/codesnippet/cpp/persistence-of-ole-controls_1.cpp)]  
[!code-cpp[NVC_MFCActiveXControl&#15;](../../mfc/codesnippet/cpp/persistence-of-ole-controls_2.cpp)]  
  
## <a name="see-also"></a>См. также  
 [Макросы и глобальные объекты](../../mfc/reference/mfc-macros-and-globals.md)

