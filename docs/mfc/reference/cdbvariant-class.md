---
title: Класс CDBVariant
ms.date: 11/04/2016
f1_keywords:
- CDBVariant
- AFXDB/CDBVariant
- AFXDB/CDBVariant::CDBVariant
- AFXDB/CDBVariant::Clear
- AFXDB/CDBVariant::m_dwType
- AFXDB/CDBVariant::m_boolVal
- AFXDB/CDBVariant::m_chVal
- AFXDB/CDBVariant::m_dblVal
- AFXDB/CDBVariant::m_fltVal
- AFXDB/CDBVariant::m_iVal
- AFXDB/CDBVariant::m_lVal
- AFXDB/CDBVariant::m_pbinary
- AFXDB/CDBVariant::m_pdate
- AFXDB/CDBVariant::m_pstring
- AFXDB/CDBVariant::m_pstringA
- AFXDB/CDBVariant::m_pstringW
helpviewer_keywords:
- CDBVariant [MFC], CDBVariant
- CDBVariant [MFC], Clear
- CDBVariant [MFC], m_dwType
- CDBVariant [MFC], m_boolVal
- CDBVariant [MFC], m_chVal
- CDBVariant [MFC], m_dblVal
- CDBVariant [MFC], m_fltVal
- CDBVariant [MFC], m_iVal
- CDBVariant [MFC], m_lVal
- CDBVariant [MFC], m_pbinary
- CDBVariant [MFC], m_pdate
- CDBVariant [MFC], m_pstring
- CDBVariant [MFC], m_pstringA
- CDBVariant [MFC], m_pstringW
ms.assetid: de23609c-c560-4b24-bd6b-9d8903fd5b49
ms.openlocfilehash: 9bb70acb43f2e73ade86b753ebbb7949759ce88d
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/22/2020
ms.locfileid: "81754597"
---
# <a name="cdbvariant-class"></a>Класс CDBVariant

Представляет вариантный тип данных для классов MFC ODBC.

## <a name="syntax"></a>Синтаксис

```
class CDBVariant
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CDBVariant::CDBVariant](#cdbvariant)|Формирует объект `CDBVariant`.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CDBVariant::Clear](#clear)|Очищает `CDBVariant` объект.|

### <a name="public-data-members"></a>Открытые члены данных

|Имя|Описание|
|----------|-----------------|
|[CDBVariant::m_dwType](#m_dwtype)|Содержит тип данных сохраненного значения. Введите `DWORD`.|

### <a name="public-union-members"></a>Члены Общественного союза

|Имя|Описание|
|----------|-----------------|
|[CDBVariant::m_boolVal](#m_boolval)|Содержит значение типа **BOOL**.|
|[CDBVariant::m_chVal](#m_chval)|Содержит значение типа **неподписанный символ**.|
|[CDBVariant::m_dblVal](#m_dblval)|Содержит значение **типа двойной**.|
|[CDBVariant::m_fltVal](#m_fltval)|Содержит значение типа **поплавка.**|
|[CDBVariant::m_iVal](#m_ival)|Содержит значение **краткого**типа .|
|[CDBVariant::m_lVal](#m_lval)|Содержит значение **длиннего**типа.|
|[CDBVariant::m_pbinary](#m_pbinary)|Содержит указатель на объект `CLongBinary`типа.|
|[CDBVariant::m_pdate](#m_pdate)|Содержит указатель на объект типа **TIMESTAMP_STRUCT.**|
|[CDBVariant::m_pstring](#m_pstring)|Содержит указатель на объект `CString`типа.|
|[CDBVariant::m_pstringA](#m_pstringa)|Хранит указатель на объект ASCII [CString.](../../atl-mfc-shared/reference/cstringt-class.md)|
|[CDBVariant::m_pstringW](#m_pstringw)|Хранит указатель на широкий объект [CString.](../../atl-mfc-shared/reference/cstringt-class.md)|

## <a name="remarks"></a>Remarks

`CDBVariant`не имеет базового класса.

`CDBVariant`похож на [COleVariant](../../mfc/reference/colevariant-class.md); однако, `CDBVariant` не использует OLE. `CDBVariant`позволяет хранить значение, не беспокоясь о типе данных значения. `CDBVariant`отслеживает тип данных текущего значения, который хранится в союзе.

Класс [CRecordset](../../mfc/reference/crecordset-class.md) `CDBVariant` использует объекты в `GetFieldValue` `GetBookmark`трех `SetBookmark`функциях члена: , и . Например, `GetFieldValue` позволяет динамически получать данные в столбце. Поскольку тип данных столбца может быть `GetFieldValue` неизвестен `CDBVariant` во время выполнения, используется объект для хранения данных столбца.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`CDBVariant`

## <a name="requirements"></a>Требования

**Заголовок:** afxdb.h

## <a name="cdbvariantcdbvariant"></a><a name="cdbvariant"></a>CDBVariant::CDBVariant

Создает объект `CDBVariant` NULL.

```
CDBVariant();
```

### <a name="remarks"></a>Remarks

Устанавливает m_dwType [данных](#m_dwtype) для DBVT_NULL.

## <a name="cdbvariantclear"></a><a name="clear"></a>CDBVariant::Clear

Вызовите эту функцию участника, чтобы очистить `CDBVariant` объект.

```cpp
void Clear();
```

### <a name="remarks"></a>Remarks

Если значение члена данных [m_dwType](#m_dwtype) является DBVT_DATE, `Clear` DBVT_STRING или DBVT_BINARY, освобождает память, связанную с членом указателя соединения. `Clear`устанавливает `m_dwType` DBVT_NULL.

Деструктор `CDBVariant` вызывает `Clear`.

## <a name="cdbvariantm_boolval"></a><a name="m_boolval"></a>CDBVariant::m_boolVal

Хранит значение типа BOOL.

### <a name="remarks"></a>Remarks

Член `m_boolVal` данных принадлежит профсоюзу. Перед доступом, `m_boolVal`сначала проверьте значение [CDBVariant::m_dwType](#m_dwtype). Если `m_dwType` установлен на DBVT_BOOL, то `m_boolVal` будет содержать допустимое значение; в противном `m_boolVal` случае доступ к ним приведет к ненадежным результатам.

## <a name="cdbvariantm_chval"></a><a name="m_chval"></a>CDBVariant::m_chVal

Хранит значение типа **неподписанный символ**.

### <a name="remarks"></a>Remarks

Член `m_chVal` данных принадлежит профсоюзу. Перед доступом, `m_chVal`сначала проверьте значение [CDBVariant::m_dwType](#m_dwtype). Если `m_dwType` установлен на DBVT_UCHAR, то `m_chVal` содержит допустимое значение; в противном `m_chVal` случае доступ к ним приведет к ненадежным результатам.

## <a name="cdbvariantm_dblval"></a><a name="m_dblval"></a>CDBVariant::m_dblVal

Хранит значение типа **двойной**.

### <a name="remarks"></a>Remarks

Член `m_dblVal` данных принадлежит профсоюзу. Перед доступом, `m_dblVal`сначала проверьте значение [CDBVariant::m_dwType](#m_dwtype). Если `m_dwType` установлен на DBVT_DOUBLE, то `m_dblVal` содержит допустимое значение; в противном `m_dblVal` случае доступ к ним приведет к ненадежным результатам.

## <a name="cdbvariantm_dwtype"></a><a name="m_dwtype"></a>CDBVariant::m_dwType

Этот член данных содержит тип данных для `CDBVariant` значения, которое в настоящее время хранится в члене союзных данных объекта.

### <a name="remarks"></a>Remarks

Прежде чем получить доступ к этому `m_dwType` союзу, вы должны проверить значение, чтобы определить, какой член данных союза для доступа. В следующей таблице перечислены `m_dwType` возможные значения для и соответствующего члена данных союза.

|m_dwType|Член союза|
|---------------|-----------------------|
|DBVT_NULL|Ни один член профсоюза не действителен для доступа.|
|DBVT_BOOL|[m_boolVal](#m_boolval)|
|DBVT_UCHAR|[m_chVal](#m_chval)|
|DBVT_SHORT|[m_iVal](#m_ival)|
|DBVT_LONG|[m_lVal](#m_lval)|
|DBVT_SINGLE|[m_fltVal](#m_fltval)|
|DBVT_DOUBLE|[m_dblVal](#m_dblval)|
|DBVT_DATE|[m_pdate](#m_pdate)|
|DBVT_STRING|[m_pstring](#m_pstring)|
|DBVT_BINARY|[m_pbinary](#m_pbinary)|
|DBVT_ASTRING|[m_pstringA](#m_pstringa)|
|DBVT_WSTRING|[m_pstringW](#m_pstringw)|

## <a name="cdbvariantm_fltval"></a><a name="m_fltval"></a>CDBVariant::m_fltVal

Хранит значение типа **поплавка.**

### <a name="remarks"></a>Remarks

Член `m_fltVal` данных принадлежит профсоюзу. Перед доступом, `m_fltVal`сначала проверьте значение [CDBVariant::m_dwType](#m_dwtype). Если `m_dwType` установлен на DBVT_SINGLE, то `m_fltVal` содержит допустимое значение; в противном `m_fltVal` случае доступ к ним приведет к ненадежным результатам.

## <a name="cdbvariantm_ival"></a><a name="m_ival"></a>CDBVariant::m_iVal

Хранит значение **краткого**типа.

### <a name="remarks"></a>Remarks

Член `m_iVal` данных принадлежит профсоюзу. Перед доступом, `m_iVal`сначала проверьте значение [CDBVariant::m_dwType](#m_dwtype). Если `m_dwType` установлен на DBVT_SHORT, то `m_iVal` содержит допустимое значение; в противном `m_iVal` случае доступ к ним приведет к ненадежным результатам.

## <a name="cdbvariantm_lval"></a><a name="m_lval"></a>CDBVariant::m_lVal

Хранит значение типа **долго**.

### <a name="remarks"></a>Remarks

Член `m_lVal` данных принадлежит профсоюзу. Перед доступом, `m_lVal`сначала проверьте значение [CDBVariant::m_dwType](#m_dwtype). Если `m_dwType` установлен на DBVT_LONG, то `m_lVal` содержит допустимое значение; в противном `m_lVal` случае доступ к ним приведет к ненадежным результатам.

## <a name="cdbvariantm_pbinary"></a><a name="m_pbinary"></a>CDBVariant::m_pbinary

Хранит указатель на объект типа [CLongBinary.](../../mfc/reference/clongbinary-class.md)

### <a name="remarks"></a>Remarks

Член `m_pbinary` данных принадлежит профсоюзу. Перед доступом, `m_pbinary`сначала проверьте значение [CDBVariant::m_dwType](#m_dwtype). Если `m_dwType` установлен на DBVT_BINARY, то `m_pbinary` содержит действительный указатель; в противном `m_pbinary` случае доступ к ним приведет к ненадежным результатам.

## <a name="cdbvariantm_pdate"></a><a name="m_pdate"></a>CDBVariant::m_pdate

Хранит указатель объекта типа TIMESTAMP_STRUCT.

### <a name="remarks"></a>Remarks

Член `m_pdate` данных принадлежит профсоюзу. Перед доступом, `m_pdate`сначала проверьте значение [CDBVariant::m_dwType](#m_dwtype). Если `m_dwType` установлен на DBVT_DATE, то `m_pdate` содержит действительный указатель; в противном `m_pdate` случае доступ к ним приведет к ненадежным результатам.

Для получения дополнительной информации о TIMESTAMP_STRUCT [C Data Types](/sql/odbc/reference/appendixes/c-data-types) типе данных, см. *ODBC Programmer's Reference*

## <a name="cdbvariantm_pstring"></a><a name="m_pstring"></a>CDBVariant::m_pstring

Хранит указатель на объект типа [CString.](../../atl-mfc-shared/reference/cstringt-class.md)

### <a name="remarks"></a>Remarks

Член `m_pstring` данных принадлежит профсоюзу. Перед доступом, `m_pstring`сначала проверьте значение [CDBVariant::m_dwType](#m_dwtype). Если `m_dwType` установлен на DBVT_STRING, то `m_pstring` содержит действительный указатель; в противном `m_pstring` случае доступ к ним приведет к ненадежным результатам.

## <a name="cdbvariantm_pstringa"></a><a name="m_pstringa"></a>CDBVariant::m_pstringA

Хранит указатель на объект ASCII [CString.](../../atl-mfc-shared/reference/cstringt-class.md)

### <a name="remarks"></a>Remarks

Член `m_pstringA` данных принадлежит профсоюзу. Перед доступом, `m_pstringA`сначала проверьте значение [CDBVariant::m_dwType](#m_dwtype). Если `m_dwType` установлен на DBVT_ASTRING, то `m_pstringA` содержит действительный указатель; в противном `m_pstringA` случае доступ к ним приведет к ненадежным результатам.

## <a name="cdbvariantm_pstringw"></a><a name="m_pstringw"></a>CDBVariant::m_pstringW

Хранит указатель на широкий объект [CString.](../../atl-mfc-shared/reference/cstringt-class.md)

### <a name="remarks"></a>Remarks

Член `m_pstringW` данных принадлежит профсоюзу. Перед доступом, `m_pstringW`сначала проверьте значение [CDBVariant::m_dwType](#m_dwtype). Если `m_dwType` установлен DBVT_WSTRING, `m_pstringW` то содержит действительный указатель; в противном `m_pstringW` случае доступ к ним приведет к ненадежным результатам.

## <a name="see-also"></a>См. также раздел

[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Класс CRecordset](../../mfc/reference/crecordset-class.md)
