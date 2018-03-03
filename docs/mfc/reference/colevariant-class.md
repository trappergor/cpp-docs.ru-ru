---
title: "Класс COleVariant | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- COleVariant
- AFXDISP/COleVariant
- AFXDISP/COleVariant::COleVariant
- AFXDISP/COleVariant::Attach
- AFXDISP/COleVariant::ChangeType
- AFXDISP/COleVariant::Clear
- AFXDISP/COleVariant::Detach
- AFXDISP/COleVariant::GetByteArrayFromVariantArray
- AFXDISP/COleVariant::SetString
dev_langs:
- C++
helpviewer_keywords:
- COleVariant [MFC], COleVariant
- COleVariant [MFC], Attach
- COleVariant [MFC], ChangeType
- COleVariant [MFC], Clear
- COleVariant [MFC], Detach
- COleVariant [MFC], GetByteArrayFromVariantArray
- COleVariant [MFC], SetString
ms.assetid: e1b5cd4a-b066-4b9b-b48b-6215ed52d998
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 3c3c9d961c69616df05975f2d484d0bbfd43f514
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="colevariant-class"></a>Класс COleVariant
Инкапсулирует тип данных [VARIANT](http://msdn.microsoft.com/en-us/e305240e-9e11-4006-98cc-26f4932d2118) .  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class COleVariant : public tagVARIANT  
```  
  
## <a name="members"></a>Участники  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[COleVariant::COleVariant](#colevariant)|Создает объект `COleVariant`.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[COleVariant::Attach](#attach)|Присоединяет **VARIANT** для `COleVariant`.|  
|[COleVariant::ChangeType](#changetype)|Изменяет тип variant этого `COleVariant` объекта.|  
|[COleVariant::Clear](#clear)|Очищает данный объект `COleVariant`.|  
|[COleVariant::Detach](#detach)|Отсоединяет **VARIANT** из `COleVariant` и возвращает **VARIANT**.|  
|[COleVariant::GetByteArrayFromVariantArray](#getbytearrayfromvariantarray)|Извлекает массив байтов из существующего массива типа variant.|  
|[COleVariant::SetString](#setstring)|Задает строку для конкретного типа, обычно ANSI.|  
  
### <a name="public-operators"></a>Открытые операторы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[COleVariant::operator LPCVARIANT](#operator_lpcvariant)|Преобразует `COleVariant` значение в `LPCVARIANT`.|  
|[COleVariant::operator LPVARIANT](#operator_lpvariant)|Преобразует `COleVariant` объекта в `LPVARIANT`.|  
|[COleVariant::operator =](#operator_eq)|Копирует `COleVariant` значение.|  
|[COleVariant::operator ==](#operator_eq_eq)|Сравнивает два `COleVariant` значения.|  
|[COleVariant::operator &lt; &lt;,&gt;&gt;](#operator_lt_lt__gt_gt)|Выходные данные `COleVariant` значение `CArchive` или `CDumpContext` и получает на входе `COleVariant` объекта из `CArchive`.|  
  
## <a name="remarks"></a>Примечания  
 Этот тип данных используется в OLE-автоматизации. В частности [DISPPARAMS](http://msdn.microsoft.com/en-us/a16e5a21-766e-4287-b039-13429aa78f8b) структура содержит указатель на массив **VARIANT** структуры. Объект **DISPPARAMS** структура используется для передачи параметров [IDispatch::Invoke](http://msdn.microsoft.com/en-us/964ade8e-9d8a-4d32-bd47-aa678912a54d).  
  
> [!NOTE]
>  Этот класс является производным от **VARIANT** структуры. Это означает, что можно передать `COleVariant` в параметр, который требует **VARIANT** и что данные-члены **VARIANT** структуры являются членами данных `COleVariant`.  
  
 Две связанные классы MFC [COleCurrency](../../mfc/reference/colecurrency-class.md) и [COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md) инкапсулируют типы данных variant **валюты** ( `VT_CY`) и **даты** ( `VT_DATE`). `COleVariant` Класс широко используется в классах DAO; см. Эти классы для типичных сценариях использования данного класса, например [CDaoQueryDef](../../mfc/reference/cdaoquerydef-class.md) и [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md).  
  
 Дополнительные сведения см. в разделе [VARIANT](http://msdn.microsoft.com/en-us/e305240e-9e11-4006-98cc-26f4932d2118), [валюты](http://msdn.microsoft.com/en-us/5e81273c-7289-45c7-93c0-32c1553f708e), [DISPPARAMS](http://msdn.microsoft.com/en-us/a16e5a21-766e-4287-b039-13429aa78f8b), и [IDispatch::Invoke](http://msdn.microsoft.com/en-us/964ade8e-9d8a-4d32-bd47-aa678912a54d) записи в Windows SDK.  
  
 Дополнительные сведения о `COleVariant` класса и его использование в OLE-автоматизации, см. в статье «Передача параметров в OLE-автоматизации» [автоматизации](../../mfc/automation.md).  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 `tagVARIANT`  
  
 `COleVariant`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxdisp.h  
  
##  <a name="attach"></a>COleVariant::Attach  
 Эта функция вызывается для присоединения заданной [VARIANT](http://msdn.microsoft.com/en-us/e305240e-9e11-4006-98cc-26f4932d2118) объект с текущим `COleVariant` объекта.  
  
```  
void Attach(VARIANT& varSrc);
```  
  
### <a name="parameters"></a>Параметры  
 *varSrc*  
 Существующий **VARIANT** объект подключен к текущей `COleVariant` объекта.  
  
### <a name="remarks"></a>Примечания  
 Эта функция задает [VARTYPE](http://msdn.microsoft.com/en-us/317b911b-1805-402d-a9cb-159546bc88b4) из *varSrc* для `VT_EMPTY`.  
  
 Дополнительные сведения см. в разделе [VARIANT](http://msdn.microsoft.com/en-us/e305240e-9e11-4006-98cc-26f4932d2118) и [VARTYPE](http://msdn.microsoft.com/en-us/317b911b-1805-402d-a9cb-159546bc88b4) записи в Windows SDK.  
  
##  <a name="colevariant"></a>COleVariant::COleVariant  
 Создает объект `COleVariant`.  
  
```  
COleVariant(); 
COleVariant(const VARIANT& varSrc); 
COleVariant(const COleVariant& varSrc); 
COleVariant(LPCVARIANT pSrc); 
COleVariant(LPCTSTR lpszSrc); 
COleVariant(LPCTSTR lpszSrc, VARTYPE vtSrc); 
COleVariant(CString& strSrc); 
COleVariant(BYTE nSrc); 
COleVariant(short nSrc, VARTYPE vtSrc = VT_I2); 
COleVariant(long lSrc,VARTYPE vtSrc = VT_I4); 
COleVariant(const COleCurrency& curSrc); 
COleVariant(float fltSrc); 
COleVariant(double dblSrc); 
COleVariant(const COleDateTime& timeSrc); 
COleVariant(const CByteArray& arrSrc); 
COleVariant(const CLongBinary& lbSrc); 
COleVariant(LPCITEMIDLIST pidl);
```  
  
### <a name="parameters"></a>Параметры  
 *varSrc*  
 Существующий `COleVariant` или **VARIANT** скопировать в новый объект `COleVariant` объекта.  
  
 `pSrc`  
 Указатель на **VARIANT** объекта, который будет скопирован в новый `COleVariant` объекта.  
  
 `lpszSrc`  
 Идентифицирующий копируются в новый `COleVariant` объекта.  
  
 `vtSrc`  
 `VARTYPE` Для нового `COleVariant` объекта.  
  
 `strSrc`  
 Объект [CString](../../atl-mfc-shared/reference/cstringt-class.md) скопировать в новый объект `COleVariant` объекта.  
  
 `nSrc`, `lSrc`  
 Числовое значение, которое необходимо скопировать в новый объект `COleVariant`.  
  
 `vtSrc`  
 `VARTYPE` Для нового `COleVariant` объекта.  
  
 `curSrc`  
 Объект [COleCurrency](../../mfc/reference/colecurrency-class.md) скопировать в новый объект `COleVariant` объекта.  
  
 `fltSrc`, `dblSrc`  
 Числовое значение, которое необходимо скопировать в новый объект `COleVariant`.  
  
 `timeSrc`  
 Объект [COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md) скопировать в новый объект `COleVariant` объекта.  
  
 `arrSrc`  
 Объект [CByteArray](../../mfc/reference/cbytearray-class.md) скопировать в новый объект `COleVariant` объекта.  
  
 `lbSrc`  
 Объект [CLongBinary](../../mfc/reference/clongbinary-class.md) скопировать в новый объект `COleVariant` объекта.  
  
 `pidl`  
 Указатель на [ITEMIDLIST](http://msdn.microsoft.com/library/windows/desktop/bb773321) структуру, чтобы скопировать в новый `COleVariant` объекта.  
  
### <a name="remarks"></a>Примечания  
 Эти конструкторы создавать новые `COleVariant` объекты, инициализированные до указанного значения. Следует краткое описание каждого из этих конструкторов.  
  
- **(COleVariant)** создает пустой `COleVariant` объекта, `VT_EMPTY`.  
  
- **COleVariant (** *varSrc* **)** копирует существующий **VARIANT** или `COleVariant` объекта. Тип variant сохранен.  
  
- **COleVariant (** `pSrc` **)** копирует существующий **VARIANT** или `COleVariant` объекта. Тип variant сохранен.  
  
- **COleVariant (** `lpszSrc` **)** копирует строку в новый объект `VT_BSTR` (Юникод).  
  
- **COleVariant (** `lpszSrc` **,** `vtSrc` **)** копирует строку в новый объект. Параметр `vtSrc` должно быть `VT_BSTR` (Юникод) или `VT_BSTRT` (ANSI).  
  
- **COleVariant (** `strSrc` **)** копирует строку в новый объект **VT_BSTR** (Юникод).  
  
- **COleVariant (** `nSrc` **)** копирует 8-разрядное целое число в новый объект `VT_UI1`.  
  
- **COleVariant (** `nSrc` **,** `vtSrc` **)** копирует 16-разрядное целое число (или логическое значение) в новый объект. Параметр `vtSrc` должно быть `VT_I2` или `VT_BOOL`.  
  
- **COleVariant (** `lSrc` **,** `vtSrc` **)** копирует 32-разрядное целое число (или `SCODE` значение) в новый объект. Параметр `vtSrc` должно быть `VT_I4`, `VT_ERROR`, или `VT_BOOL`.  
  
- **COleVariant (** `curSrc` **)** копии **COleCurrency** значения в новый объект `VT_CY`.  
  
- **COleVariant (** `fltSrc` **)** копирует 32-разрядное значение с плавающей запятой в новый объект `VT_R4`.  
  
- **COleVariant (** `dblSrc` **)** копирует 64-разрядное значение с плавающей запятой в новый объект `VT_R8`.  
  
- **COleVariant (** `timeSrc` **)** копии `COleDateTime` значения в новый объект `VT_DATE`.  
  
- **COleVariant (** `arrSrc` **)** копии `CByteArray` объекта в новый объект `VT_EMPTY`.  
  
- **COleVariant (** `lbSrc` **)** копии `CLongBinary` объекта в новый объект `VT_EMPTY`.  
  
 Дополнительные сведения о `SCODE`, в разделе [структуры из кодов ошибок модели COM](http://msdn.microsoft.com/library/windows/desktop/ms690088) в Windows SDK.  
  
##  <a name="changetype"></a>COleVariant::ChangeType  
 Преобразует тип variant значения в этом `COleVariant` объекта.  
  
```  
void ChangeType(VARTYPE vartype, LPVARIANT pSrc = NULL);
```  
  
### <a name="parameters"></a>Параметры  
 `vartype`  
 [VARTYPE](http://msdn.microsoft.com/en-us/317b911b-1805-402d-a9cb-159546bc88b4) для этого `COleVariant` объекта.  
  
 `pSrc`  
 Указатель на [VARIANT](http://msdn.microsoft.com/en-us/e305240e-9e11-4006-98cc-26f4932d2118) преобразуемого объекта. Если это значение равно **NULL**, то `COleVariant` объект используется в качестве источника для преобразования.  
  
### <a name="remarks"></a>Примечания  
 Дополнительные сведения см. в разделе [VARIANT](http://msdn.microsoft.com/en-us/e305240e-9e11-4006-98cc-26f4932d2118), [VARTYPE](http://msdn.microsoft.com/en-us/317b911b-1805-402d-a9cb-159546bc88b4), и [VariantChangeType](http://msdn.microsoft.com/en-us/48a51e32-95d7-4eeb-8106-f5043ffa2fd1) записи в Windows SDK.  
  
##  <a name="clear"></a>COleVariant::Clear  
 Очищает **VARIANT**.  
  
```  
void Clear();
```  
  
### <a name="remarks"></a>Примечания  
 Это задает **VARTYPE** для этого объекта `VT_EMPTY`. `COleVariant` Деструктор вызывает эту функцию.  
  
 Дополнительные сведения см. в разделе `VARIANT`, `VARTYPE`, и `VariantClear` записи в Windows SDK.  
  
##  <a name="detach"></a>COleVariant::Detach  
 Отсоединяет базовый [VARIANT](http://msdn.microsoft.com/en-us/e305240e-9e11-4006-98cc-26f4932d2118) объекта из этого `COleVariant` объекта.  
  
```  
VARIANT Detach();
```  
  
### <a name="remarks"></a>Примечания  
 Эта функция задает [VARTYPE](http://msdn.microsoft.com/en-us/317b911b-1805-402d-a9cb-159546bc88b4) для этого `COleVariant` объект `VT_EMPTY`.  
  
> [!NOTE]
>  После вызова метода **отсоединения**, вызывающего обязан вызвать **VariantClear** полученного в результате **VARIANT** структуры.  
  
 Дополнительные сведения см. в разделе [VARIANT](http://msdn.microsoft.com/en-us/e305240e-9e11-4006-98cc-26f4932d2118), [VARTYPE](http://msdn.microsoft.com/en-us/317b911b-1805-402d-a9cb-159546bc88b4), и [VariantClear](http://msdn.microsoft.com/en-us/28741d81-8404-4f85-95d3-5c209ec13835) записи в Windows SDK.  
  
##  <a name="getbytearrayfromvariantarray"></a>COleVariant::GetByteArrayFromVariantArray  
 Извлекает массив байтов из существующего массива типа variant  
  
```  
void GetByteArrayFromVariantArray(CByteArray& bytes);
```  
  
### <a name="parameters"></a>Параметры  
 `bytes`  
 Ссылка на существующий [CByteArray](../../mfc/reference/cbytearray-class.md) объекта.  
  
##  <a name="operator_lpcvariant"></a>COleVariant::operator LPCVARIANT  
 Этот оператор приведения возвращает `VARIANT` , значение которого копируется из этой структуры `COleVariant` объекта.  
  
```  
operator LPCVARIANT() const; 
```  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="operator_lpvariant"></a>COleVariant::operator LPVARIANT  
 Вызовите этот оператор приведения для доступа к базовым `VARIANT` структуры для этого `COleVariant` объекта.  
  
```  
operator LPVARIANT();
```   
  
### <a name="remarks"></a>Примечания  
  
> [!CAUTION]
>  Изменение значения в **VARIANT** структуры обращаются указатель, возвращаемый этой функцией изменит значение этой `COleVariant` объекта.  
  
##  <a name="operator_eq"></a>COleVariant::operator =  
 Эти перегруженных операторах присваивания копирования исходного значения в это `COleVariant` объекта.  
  
```  
const COleVariant& operator=(const VARIANT& varSrc); 
const COleVariant& operator=(LPCVARIANT pSrc); 
const COleVariant& operator=(const COleVariant& varSrc); 
const COleVariant& operator=(const LPCTSTR lpszSrc);
const COleVariant& operator=(const CString& strSrc); 
const COleVariant& operator=(BYTE nSrc); 
const COleVariant& operator=(short nSrc); 
const COleVariant& operator=(long lSrc); 
const COleVariant& operator=(const COleCurrency& curSrc); 
const COleVariant& operator=(float fltSrc); 
const COleVariant& operator=(double dblSrc); 
const COleVariant& operator=(const COleDateTime& dateSrc); 
const COleVariant& operator=(const CByteArray& arrSrc); 
const COleVariant& operator=(const CLongBinary& lbSrc);
```  
  
### <a name="remarks"></a>Примечания  
 Краткое описание каждого оператора выглядит следующим образом:  
  
- **оператор = (** *varSrc***)** копирует существующий **VARIANT** или `COleVariant` объект в этот объект.  
  
- **оператор = (** `pSrc` **)** копии **VARIANT** осуществляется из объекта `pSrc` в этот объект.  
  
- **оператор = (** `lpszSrc` **)** копирует строку, завершающуюся значением null в этот объект и задает **VARTYPE** для `VT_BSTR`.  
  
- **оператор = (** `strSrc` **)** копии [CString](../../atl-mfc-shared/reference/cstringt-class.md) объект в этот объект и задает **VARTYPE** для `VT_BSTR`.  
  
- **оператор = (** `nSrc` **)** копирует в этот объект 8 или 16-разрядное целочисленное значение. Если `nSrc` представляет 8-разрядное значение **VARTYPE** данного объекта имеет значение `VT_UI1`. Если `nSrc` представляет 16-разрядное значение и **VARTYPE** является данный `VT_BOOL`, он сохраняется; в противном случае, он становится равным `VT_I2`.  
  
- **оператор = (** `lSrc` **)** копирует в этот объект 32-разрядное целочисленное значение. Если **VARTYPE** является данный `VT_ERROR`, он сохраняется; в противном случае, он становится равным `VT_I4`.  
  
- **оператор = (** `curSrc` **)** копии [COleCurrency](../../mfc/reference/colecurrency-class.md) объект в этот объект и задает **VARTYPE** для `VT_CY`.  
  
- **оператор = (** `fltSrc` **)** копирует 32-разрядное значение с плавающей запятой в этот объект и задает **VARTYPE** для `VT_R4`.  
  
- **оператор = (** `dblSrc` **)** копирует 64-разрядное значение с плавающей запятой в этот объект и задает **VARTYPE** для `VT_R8`.  
  
- **оператор = (** `dateSrc` **)** копии [COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md) объект в этот объект и задает **VARTYPE** для `VT_DATE`.  
  
- **оператор = (** `arrSrc` **)** копии [CByteArray](../../mfc/reference/cbytearray-class.md) объект в этот `COleVariant` объекта.  
  
- **оператор = (** `lbSrc` **)** копии [CLongBinary](../../mfc/reference/clongbinary-class.md) объект в этот `COleVariant` объекта.  
  
 Дополнительные сведения см. в разделе [VARIANT](http://msdn.microsoft.com/en-us/e305240e-9e11-4006-98cc-26f4932d2118) и [VARTYPE](http://msdn.microsoft.com/en-us/317b911b-1805-402d-a9cb-159546bc88b4) записи в Windows SDK.  
  
##  <a name="operator_eq_eq"></a>COleVariant::operator ==  
 Этот оператор сравнивает два значения типа variant и возвращает ненулевое значение, если объекты равны; в противном случае — 0.  
  
```  
BOOL operator==(const VARIANT& varSrc) const; 
BOOL operator==(LPCVARIANT pSrc) const;
```  
  
##  <a name="operator_lt_lt__gt_gt"></a>COleVariant::operator &lt; &lt;,&gt;&gt;  
 Выходные данные `COleVariant` значение `CArchive` или **CdumpContext** и получает на входе `COleVariant` объекта из `CArchive`.  
  
```  
friend CDumpContext& AFXAPI operator<<(
    CDumpContext& dc,  
    OleVariant varSrc);
 
friend CArchive& AFXAPI operator<<(
    CArchive& ar,  
    COleVariant varSrc);
 
friend CArchive& AFXAPI operator>>(
    CArchive& ar,  
    COleVariant& varSrc);
```  
  
### <a name="remarks"></a>Примечания  
 `COleVariant` Вставки (  **< \<** ) поддерживает оператор диагностики формирование дампа и хранение в архив. Извлечение (  **>>** ) оператор поддерживает загрузку из архива.  
  
##  <a name="setstring"></a>COleVariant::SetString  
 Задает строку для конкретного типа.  
  
```  
void SetString(LPCTSTR lpszSrc, VARTYPE vtSrc);
```  
  
### <a name="parameters"></a>Параметры  
 `lpszSrc`  
 Идентифицирующий копируются в новый `COleVariant` объекта.  
  
 *VtSrc*  
 **VARTYPE** для нового `COleVariant` объекта.  
  
### <a name="remarks"></a>Примечания  
 Параметр `vtSrc` должно быть `VT_BSTR` (Юникод) или `VT_BSTRT` (ANSI). `SetString`обычно используется значение строки ANSI, поскольку значение по умолчанию для [COleVariant::COleVariant](#colevariant) конструктор со строкой или указатель строковый параметр и не **VARTYPE** имеет формат ЮНИКОДА.  
  
 Набор записей DAO в сборке не в ЮНИКОДЕ ожидает, что строки, строки ANSI. Таким образом, для DAO функции, использующие `COleVariant` объектов, если вы не создаете набор записей Юникод, необходимо использовать **COleVariant::COleVariant (** `lpszSrc` **,** `vtSrc` **)**  форма конструктора с `vtSrc` значение `VT_BSTRT` (ANSI) или использовать `SetString` с `vtSrc` значение `VT_BSTRT` вносить строк в кодировке ANSI. Например `CDaoRecordset` функции [CDaoRecordset::Seek](../../mfc/reference/cdaorecordset-class.md#seek) и [CDaoRecordset::SetFieldValue](../../mfc/reference/cdaorecordset-class.md#setfieldvalue) использовать `COleVariant` объектов как параметры. Эти объекты должны быть ANSI, если набор записей DAO не в ЮНИКОДЕ.  
  
## <a name="see-also"></a>См. также  
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)



