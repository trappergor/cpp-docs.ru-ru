---
title: Класс COleVariant | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 8b7501adf2f424f2232df05e26f5d0ac4a35158c
ms.sourcegitcommit: b92ca0b74f0b00372709e81333885750ba91f90e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/16/2018
ms.locfileid: "42541507"
---
# <a name="colevariant-class"></a>Класс COleVariant
Инкапсулирует [VARIANT](/previous-versions/windows/desktop/api/oaidl/ns-oaidl-tagvariant) тип данных.  
  
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
|[COleVariant::Attach](#attach)|Присоединяет типа VARIANT в `COleVariant`.|  
|[COleVariant::ChangeType](#changetype)|Изменяет тип варианта этого `COleVariant` объекта.|  
|[COleVariant::Clear](#clear)|Очищает данный объект `COleVariant`.|  
|[COleVariant::Detach](#detach)|Отсоединяет VARIANT из `COleVariant` и возвращает тип VARIANT.|  
|[COleVariant::GetByteArrayFromVariantArray](#getbytearrayfromvariantarray)|Извлекает массив байтов из существующего массива variant.|  
|[COleVariant::SetString](#setstring)|Задает строку для определенного типа, обычно ANSI.|  
  
### <a name="public-operators"></a>Открытые операторы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[COleVariant::operator LPCVARIANT](#operator_lpcvariant)|Преобразует `COleVariant` значение в `LPCVARIANT`.|  
|[COleVariant::operator LPVARIANT](#operator_lpvariant)|Преобразует `COleVariant` в коллекцию `LPVARIANT`.|  
|[COleVariant::operator =](#operator_eq)|Копирует `COleVariant` значение.|  
|[COleVariant::operator ==](#operator_eq_eq)|Сравнивает два `COleVariant` значения.|  
|[COleVariant::operator &lt; &lt;, &gt;&gt;](#operator_lt_lt__gt_gt)|Выходные данные `COleVariant` значение `CArchive` или `CDumpContext` и вводит `COleVariant` объекта из `CArchive`.|  
  
## <a name="remarks"></a>Примечания  
 Этот тип данных используется в OLE-автоматизации. В частности [DISPPARAMS](/previous-versions/windows/desktop/api/oaidl/ns-oaidl-tagdispparams) структура содержит указатель на массив структур VARIANT. Объект `DISPPARAMS` структура используется для передачи параметров [IDispatch::Invoke](/previous-versions/windows/desktop/api/oaidl/nf-oaidl-idispatch-invoke).  
  
> [!NOTE]
>  Этот класс является производным от `VARIANT` структуры. Это означает, что вы можете передать `COleVariant` в параметр, который требует `VARIANT` и что члены данных `VARIANT` структуры являются членами доступные данные `COleVariant`.  
  
 Две связанные классы MFC [COleCurrency](../../mfc/reference/colecurrency-class.md) и [COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md) инкапсулировать типов данных variant валюты ( `VT_CY`) и DATE ( `VT_DATE`). `COleVariant` Класс широко используется в классах DAO; см. в статье эти классы обычно данного класса, например [CDaoQueryDef](../../mfc/reference/cdaoquerydef-class.md) и [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md).  
  
 Дополнительные сведения см. в разделе [VARIANT](/previous-versions/windows/desktop/api/oaidl/ns-oaidl-tagvariant), [валюты](http://msdn.microsoft.com/5e81273c-7289-45c7-93c0-32c1553f708e), [DISPPARAMS](/previous-versions/windows/desktop/api/oaidl/ns-oaidl-tagdispparams), и [IDispatch::Invoke](/previous-versions/windows/desktop/api/oaidl/nf-oaidl-idispatch-invoke) записей в пакете Windows SDK.  
  
 Дополнительные сведения о `COleVariant` класса и его использование в OLE-автоматизации, см. в разделе «Передача параметров в OLE-автоматизации» в статье [автоматизации](../../mfc/automation.md).  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 `tagVARIANT`  
  
 `COleVariant`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxdisp.h  
  
##  <a name="attach"></a>  COleVariant::Attach  
 Вызывайте эту функцию для присоединения заданной [VARIANT](/previous-versions/windows/desktop/api/oaidl/ns-oaidl-tagvariant) объект с текущим `COleVariant` объекта.  
  
```  
void Attach(VARIANT& varSrc);
```  
  
### <a name="parameters"></a>Параметры  
 *varSrc*  
 Существующий `VARIANT` объекта должны быть присоединены к текущим `COleVariant` объекта.  
  
### <a name="remarks"></a>Примечания  
 Эта функция задает [VARTYPE](http://msdn.microsoft.com/317b911b-1805-402d-a9cb-159546bc88b4) из *varSrc* значение VT_EMPTY.  
  
 Дополнительные сведения см. в разделе [VARIANT](/previous-versions/windows/desktop/api/oaidl/ns-oaidl-tagvariant) и [VARTYPE](http://msdn.microsoft.com/317b911b-1805-402d-a9cb-159546bc88b4) записей в пакете Windows SDK.  
  
##  <a name="colevariant"></a>  COleVariant::COleVariant  
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
 Существующий `COleVariant` или `VARIANT` объект, который необходимо скопировать в новый `COleVariant` объекта.  
  
 *pSrc*  
 Указатель на `VARIANT` объект, который будет скопирован в новый `COleVariant` объекта.  
  
 *lpszSrc*  
 Заканчивающуюся нулем строку, который необходимо скопировать в новый `COleVariant` объекта.  
  
 *vtSrc*  
 `VARTYPE` Для нового `COleVariant` объекта.  
  
 *strSrc*  
 Объект [CString](../../atl-mfc-shared/reference/cstringt-class.md) объект, который необходимо скопировать в новый `COleVariant` объекта.  
  
 *nSrc*, *lSrc*  
 Числовое значение, которое необходимо скопировать в новый объект `COleVariant`.  
  
 *vtSrc*  
 `VARTYPE` Для нового `COleVariant` объекта.  
  
 *curSrc*  
 Объект [COleCurrency](../../mfc/reference/colecurrency-class.md) объект, который необходимо скопировать в новый `COleVariant` объекта.  
  
 *fltSrc*, *dblSrc*  
 Числовое значение, которое необходимо скопировать в новый объект `COleVariant`.  
  
 *timeSrc*  
 Объект [COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md) объект, который необходимо скопировать в новый `COleVariant` объекта.  
  
 *arrSrc*  
 Объект [CByteArray](../../mfc/reference/cbytearray-class.md) объект, который необходимо скопировать в новый `COleVariant` объекта.  
  
 *lbSrc*  
 Объект [CLongBinary](../../mfc/reference/clongbinary-class.md) объект, который необходимо скопировать в новый `COleVariant` объекта.  
  
 *pidl*  
 Указатель на [ITEMIDLIST](http://msdn.microsoft.com/library/windows/desktop/bb773321) структуры, который необходимо скопировать в новый `COleVariant` объекта.  
  
### <a name="remarks"></a>Примечания  
 Эти конструкторы создавать новые `COleVariant` объекты, инициализированные указанное значение. Следует краткое описание каждого из этих конструкторов.  
  
- **() COleVariant** создает пустой `COleVariant` объект, значение VT_EMPTY.  
  
- **COleVariant (** *varSrc* **)** копирует существующий `VARIANT` или `COleVariant` объекта. Тип variant сохранен.  
  
- **COleVariant (** `pSrc` **)** копирует существующий `VARIANT` или `COleVariant` объекта. Тип variant сохранен.  
  
- **COleVariant (** `lpszSrc` **)** копирует строки в новый объект VT_BSTR (Юникод).  
  
- **COleVariant (** `lpszSrc` **,** `vtSrc` **)** копирует строки в новый объект. Параметр *vtSrc* должно быть VT_BSTR (Юникод) или VT_BSTRT (ANSI).  
  
- **COleVariant (** `strSrc` **)** копирует строки в новый объект VT_BSTR (Юникод).  
  
- **COleVariant (** `nSrc` **)** копирует в этот новый объект VT_UI1 8-разрядное целое число.  
  
- **COleVariant (** `nSrc` **,** `vtSrc` **)** копирует 16-разрядное целое число (или логическое значение) в новый объект. Параметр *vtSrc* должно быть VT_I2 или VT_BOOL.  
  
- **COleVariant (** `lSrc` **,** `vtSrc` **)** копирует 32-разрядное целое число (или значение SCODE) в новый объект. Параметр *vtSrc* должно быть VT_I4, VT_ERROR или VT_BOOL.  
  
- **COleVariant (** `curSrc` **)** копий `COleCurrency` значение в новый объект, VT_CY.  
  
- **COleVariant (** `fltSrc` **)** копирует в этот новый объект VT_R4 32-разрядное значение с плавающей запятой.  
  
- **COleVariant (** `dblSrc` **)** копирует значение с плавающей запятой 64-разрядных в новый объект VT_R8.  
  
- **COleVariant (** `timeSrc` **)** копий `COleDateTime` значение в новый объект, VT_DATE.  
  
- **COleVariant (** `arrSrc` **)** копий `CByteArray` объекта в новый объект, значение VT_EMPTY.  
  
- **COleVariant (** `lbSrc` **)** копий `CLongBinary` объекта в новый объект, значение VT_EMPTY.  
  
 Дополнительные сведения о SCODE, см. в разделе [структуры из кодов ошибок модели COM](http://msdn.microsoft.com/library/windows/desktop/ms690088) в пакете Windows SDK.  
  
##  <a name="changetype"></a>  COleVariant::ChangeType  
 Преобразует тип значения типа variant в этом `COleVariant` объекта.  
  
```  
void ChangeType(VARTYPE vartype, LPVARIANT pSrc = NULL);
```  
  
### <a name="parameters"></a>Параметры  
 *VarType*  
 [VARTYPE](http://msdn.microsoft.com/317b911b-1805-402d-a9cb-159546bc88b4) для данного `COleVariant` объекта.  
  
 *pSrc*  
 Указатель на [VARIANT](/previous-versions/windows/desktop/api/oaidl/ns-oaidl-tagvariant) преобразуемого объекта. Если это значение равно NULL, это `COleVariant` объект используется в качестве источника для преобразования.  
  
### <a name="remarks"></a>Примечания  
 Дополнительные сведения см. в разделе [VARIANT](/previous-versions/windows/desktop/api/oaidl/ns-oaidl-tagvariant), [VARTYPE](http://msdn.microsoft.com/317b911b-1805-402d-a9cb-159546bc88b4), и [VariantChangeType](/previous-versions/windows/desktop/api/oleauto/nf-oleauto-variantchangetype) записей в пакете Windows SDK.  
  
##  <a name="clear"></a>  COleVariant::Clear  
 Очищает `VARIANT`.  
  
```  
void Clear();
```  
  
### <a name="remarks"></a>Примечания  
 Таким образом задается VARTYPE для данного объекта значение VT_EMPTY. `COleVariant` Деструктор вызывает эту функцию.  
  
 Дополнительные сведения см. в разделе `VARIANT`, тип ПЕРЕМЕННОЙ, и `VariantClear` записей в пакете Windows SDK.  
  
##  <a name="detach"></a>  COleVariant::Detach  
 Отсоединяет базовый [VARIANT](/previous-versions/windows/desktop/api/oaidl/ns-oaidl-tagvariant) из данного `COleVariant` объекта.  
  
```  
VARIANT Detach();
```  
  
### <a name="remarks"></a>Примечания  
 Эта функция задает [VARTYPE](http://msdn.microsoft.com/317b911b-1805-402d-a9cb-159546bc88b4) для данного `COleVariant` объекта значение VT_EMPTY.  
  
> [!NOTE]
>  После вызова метода `Detach`, вызывающего обязан вызвать `VariantClear` в результате `VARIANT` структуры.  
  
 Дополнительные сведения см. в разделе [VARIANT](/previous-versions/windows/desktop/api/oaidl/ns-oaidl-tagvariant), [VARTYPE](http://msdn.microsoft.com/317b911b-1805-402d-a9cb-159546bc88b4), и [VariantClear](/previous-versions/windows/desktop/api/oleauto/nf-oleauto-variantclear) записей в пакете Windows SDK.  
  
##  <a name="getbytearrayfromvariantarray"></a>  COleVariant::GetByteArrayFromVariantArray  
 Извлекает массив байтов из существующего массива variant  
  
```  
void GetByteArrayFromVariantArray(CByteArray& bytes);
```  
  
### <a name="parameters"></a>Параметры  
 *байт*  
 Ссылка на существующий [CByteArray](../../mfc/reference/cbytearray-class.md) объекта.  
  
##  <a name="operator_lpcvariant"></a>  COleVariant::operator LPCVARIANT  
 Этот оператор приведения типов возвращает `VARIANT` структуры, значение которого копируется из этого `COleVariant` объекта.  
  
```  
operator LPCVARIANT() const; 
```  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="operator_lpvariant"></a>  COleVariant::operator LPVARIANT  
 Вызовите этот оператор приведения, чтобы получить доступ к базовой `VARIANT` структуры для этого `COleVariant` объекта.  
  
```  
operator LPVARIANT();
```   
  
### <a name="remarks"></a>Примечания  
  
> [!CAUTION]
>  Изменение значения в `VARIANT` структуры осуществляется указатель, возвращаемый этой функцией изменится значение этой `COleVariant` объекта.  
  
##  <a name="operator_eq"></a>  COleVariant::operator =  
 Эти перегруженных операторах присваивания копирования исходного значения в данный `COleVariant` объекта.  
  
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
  
- **оператор = (** *varSrc ***)** копирует существующему ВАРИАНТУ или `COleVariant` объект в этот объект.  
  
- **оператор = (** `pSrc` **)** копирует объект типа VARIANT, к которому *pSrc* в этот объект.  
  
- **оператор = (** `lpszSrc` **)** копирует заканчивающуюся нулем строку, в этот объект и задает VARTYPE VT_BSTR.  
  
- **оператор = (** `strSrc` **)** копий [CString](../../atl-mfc-shared/reference/cstringt-class.md) в этот объект и наборы VARTYPE значение VT_BSTR объект.  
  
- **оператор = (** `nSrc` **)** копирует 8 или 16-разрядное целочисленное значение в этот объект. Если *nSrc* является 8-разрядное значение, имеет значение VARTYPE этого VT_UI1. Если *nSrc* является 16-разрядное значение и VARTYPE этого является VT_BOOL, его сохранить, иначе, он становится равным VT_I2.  
  
- **оператор = (** `lSrc` **)** копирует значение 32-разрядное целое число в этот объект. Если VARTYPE этого VT_ERROR, она хранится в; в противном случае ему присваивается VT_I4.  
  
- **оператор = (** `curSrc` **)** копий [COleCurrency](../../mfc/reference/colecurrency-class.md) объект в этот объект и наборы VARTYPE для VT_CY.  
  
- **оператор = (** `fltSrc` **)** копирует 32-разрядное значение с плавающей запятой в этот объект и задает VARTYPE VT_R4.  
  
- **оператор = (** `dblSrc` **)** копирует значение с плавающей запятой 64-разрядных в этот объект и задает VARTYPE VT_R8.  
  
- **оператор = (** `dateSrc` **)** копий [COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md) объект в этот объект и наборы VARTYPE для VT_DATE.  
  
- **оператор = (** `arrSrc` **)** копий [CByteArray](../../mfc/reference/cbytearray-class.md) в этот объект `COleVariant` объекта.  
  
- **оператор = (** `lbSrc` **)** копий [CLongBinary](../../mfc/reference/clongbinary-class.md) в этот объект `COleVariant` объекта.  
  
 Дополнительные сведения см. в разделе [VARIANT](/previous-versions/windows/desktop/api/oaidl/ns-oaidl-tagvariant) и [VARTYPE](http://msdn.microsoft.com/317b911b-1805-402d-a9cb-159546bc88b4) записей в пакете Windows SDK.  
  
##  <a name="operator_eq_eq"></a>  COleVariant::operator ==  
 Этот оператор сравнивает два значения типа variant и возвращает ненулевое значение, если они равны; в противном случае 0.  
  
```  
BOOL operator==(const VARIANT& varSrc) const; 
BOOL operator==(LPCVARIANT pSrc) const;
```  
  
##  <a name="operator_lt_lt__gt_gt"></a>  COleVariant::operator &lt; &lt;, &gt;&gt;  
 Выходные данные `COleVariant` значение `CArchive` или `CdumpContext` и вводит `COleVariant` объекта из `CArchive`.  
  
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
 `COleVariant` Вставки ( **< \<**) поддерживает оператор диагностики создания дампа и хранения в архив. Извлечение ( **>>**) оператор поддерживает загрузку из архива.  
  
##  <a name="setstring"></a>  COleVariant::SetString  
 Задает строку для определенного типа.  
  
```  
void SetString(LPCTSTR lpszSrc, VARTYPE vtSrc);
```  
  
### <a name="parameters"></a>Параметры  
 *lpszSrc*  
 Заканчивающуюся нулем строку, который необходимо скопировать в новый `COleVariant` объекта.  
  
 *vtSrc*  
 VARTYPE для нового `COleVariant` объекта.  
  
### <a name="remarks"></a>Примечания  
 Параметр *vtSrc* должно быть VT_BSTR (Юникод) или VT_BSTRT (ANSI). `SetString` обычно используется для значение строки ANSI, поскольку по умолчанию для [COleVariant::COleVariant](#colevariant) конструктор со строкой или параметр указателя на строку и не VARTYPE — Юникод.  
  
 Набор записей DAO в сборке не в ЮНИКОДЕ ожидает, что строки в кодировке ANSI. Таким образом, для DAO функции, использующие `COleVariant` объекты, если вы не создаете набор Юникод, необходимо использовать **COleVariant::COleVariant (** `lpszSrc` **,** `vtSrc` **)**  форма конструктора с *vtSrc* задать VT_BSTRT (ANSI) или использовать `SetString` с *vtSrc* задайте VT_BSTRT, чтобы сделать строк в кодировке ANSI. Например `CDaoRecordset` функции [CDaoRecordset::Seek](../../mfc/reference/cdaorecordset-class.md#seek) и [CDaoRecordset::SetFieldValue](../../mfc/reference/cdaorecordset-class.md#setfieldvalue) использовать `COleVariant` объектов в качестве параметров. Эти объекты должны быть ANSI, если набор записей DAO работает не в ЮНИКОДЕ.  
  
## <a name="see-also"></a>См. также  
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)



