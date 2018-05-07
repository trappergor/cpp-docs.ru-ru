---
title: CDBVariant-класс | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
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
dev_langs:
- C++
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 27970a7d3854dca398943bfe13c67f6a4e1f92f5
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="cdbvariant-class"></a>CDBVariant-класс
Представляет вариантный тип данных для классов MFC ODBC.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CDBVariant  
```  
  
## <a name="members"></a>Члены  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CDBVariant::CDBVariant](#cdbvariant)|Создает объект `CDBVariant`.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CDBVariant::Clear](#clear)|Очищает `CDBVariant` объекта.|  
  
### <a name="public-data-members"></a>Открытые члены данных  
  
|Имя|Описание|  
|----------|-----------------|  
|[CDBVariant::m_dwType](#m_dwtype)|Содержит тип данных в данный момент сохраненного значения. Введите `DWORD`.|  
  
### <a name="public-union-members"></a>Открытые члены объединения  
  
|Имя|Описание|  
|----------|-----------------|  
|[CDBVariant::m_boolVal](#m_boolval)|Содержит значение типа **BOOL**.|  
|[CDBVariant::m_chVal](#m_chval)|Содержит значение типа `unsigned char`.|  
|[CDBVariant::m_dblVal](#m_dblval)|Содержит значение типа **двойные**.|  
|[CDBVariant::m_fltVal](#m_fltval)|Содержит значение типа **float**.|  
|[CDBVariant::m_iVal](#m_ival)|Содержит значение типа **короткие**.|  
|[CDBVariant::m_lVal](#m_lval)|Содержит значение типа **длинные**.|  
|[CDBVariant::m_pbinary](#m_pbinary)|Содержит указатель на объект типа `CLongBinary`.|  
|[CDBVariant::m_pdate](#m_pdate)|Содержит указатель на объект типа **TIMESTAMP_STRUCT**.|  
|[CDBVariant::m_pstring](#m_pstring)|Содержит указатель на объект типа `CString`.|  
|[CDBVariant::m_pstringA](#m_pstringa)|Содержит указатель на ASCII [CString](../../atl-mfc-shared/reference/cstringt-class.md) объекта.|  
|[CDBVariant::m_pstringW](#m_pstringw)|Содержит указатель на уровне [CString](../../atl-mfc-shared/reference/cstringt-class.md) объекта.|  
  
## <a name="remarks"></a>Примечания  
 `CDBVariant` не имеет базового класса.  
  
 `CDBVariant` Аналогично [COleVariant](../../mfc/reference/colevariant-class.md), однако `CDBVariant` не использует OLE. `CDBVariant` Позволяет хранить значения, не беспокоясь о типами данных. `CDBVariant` отслеживает текущее значение, которое хранится в объединении тип данных.  
  
 Класс [CRecordset](../../mfc/reference/crecordset-class.md) использует `CDBVariant` объектов в трех функций-членов: `GetFieldValue`, `GetBookmark`, и `SetBookmark`. Например `GetFieldValue` позволяет динамически извлекать данные в столбце. Так как тип данных столбца не может быть известен во время выполнения `GetFieldValue` использует `CDBVariant` объект для хранения данных в столбце.  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 `CDBVariant`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxdb.h  
  
##  <a name="cdbvariant"></a>  CDBVariant::CDBVariant  
 Создает значение NULL `CDBVariant` объекта.  
  
```  
CDBVariant();
```  
  
### <a name="remarks"></a>Примечания  
 Наборы [m_dwType](#m_dwtype) данные-члены **DBVT_NULL**.  
  
##  <a name="clear"></a>  CDBVariant::Clear  
 Вызовите эту функцию-член для очистки `CDBVariant` объекта.  
  
```  
void Clear();
```  
  
### <a name="remarks"></a>Примечания  
 Если значение [m_dwType](#m_dwtype) член данных — **DBVT_DATE**, **DBVT_STRING**, или **DBVT_BINARY**, **снимите**освобождает память, связанные с членом объединения указателя. **Очистить** задает `m_dwType` для **DBVT_NULL**.  
  
 `CDBVariant` Вызовы деструктора **снимите**.  
  
##  <a name="m_boolval"></a>  CDBVariant::m_boolVal  
 Сохраняет значение типа **BOOL**.  
  
### <a name="remarks"></a>Примечания  
 **M_boolVal** элемент данных относится к объединению. Перед обращением к **m_boolVal**, сначала проверьте значение [CDBVariant::m_dwType](#m_dwtype). Если `m_dwType` равно **DBVT_BOOL**, затем **m_boolVal** будет содержать допустимое значение; в противном случае доступ к **m_boolVal** приведет к недостоверным результатам.  
  
##  <a name="m_chval"></a>  CDBVariant::m_chVal  
 Сохраняет значение типа `unsigned char`.  
  
### <a name="remarks"></a>Примечания  
 **M_chVal** элемент данных относится к объединению. Перед обращением к **m_chVal**, сначала проверьте значение [CDBVariant::m_dwType](#m_dwtype). Если `m_dwType` равно **DBVT_UCHAR**, затем **m_chVal** содержит допустимое значение; в противном случае доступ к **m_chVal** приведет к недостоверным результатам.  
  
##  <a name="m_dblval"></a>  CDBVariant::m_dblVal  
 Сохраняет значение типа **двойные**.  
  
### <a name="remarks"></a>Примечания  
 **M_dblVal** элемент данных относится к объединению. Перед обращением к **m_dblVal**, сначала проверьте значение [CDBVariant::m_dwType](#m_dwtype). Если `m_dwType` равно **DBVT_DOUBLE**, затем **m_dblVal** содержит допустимое значение; в противном случае доступ к **m_dblVal** приведет к недостоверным результатам.  
  
##  <a name="m_dwtype"></a>  CDBVariant::m_dwType  
 Этот элемент данных содержит тип данных для значения, которое в настоящее время хранятся в `CDBVariant` члену объекта объединения данных.  
  
### <a name="remarks"></a>Примечания  
 Перед обращением к это объединение, необходимо проверить значение `m_dwType` , чтобы определить, какой элемент объединения данных для доступа к. В следующей таблице перечислены возможные значения для `m_dwType` и соответствующий элемент объединения данных.  
  
|m_dwType|Элемент объединения данных|  
|---------------|-----------------------|  
|**DBVT_NULL**|Нет элемент объединения является допустимым для доступа.|  
|**DBVT_BOOL**|[m_boolVal](#m_boolval)|  
|**DBVT_UCHAR**|[m_chVal](#m_chval)|  
|**DBVT_SHORT**|[m_iVal](#m_ival)|  
|**DBVT_LONG**|[m_lVal](#m_lval)|  
|**DBVT_SINGLE**|[m_fltVal](#m_fltval)|  
|**DBVT_DOUBLE**|[m_dblVal](#m_dblval)|  
|**DBVT_DATE**|[m_pdate](#m_pdate)|  
|**DBVT_STRING**|[m_pstring](#m_pstring)|  
|**DBVT_BINARY**|[m_pbinary](#m_pbinary)|  
|**DBVT_ASTRING**|[m_pstringA](#m_pstringa)|  
|**DBVT_WSTRING**|[m_pstringW](#m_pstringw)|  
  
##  <a name="m_fltval"></a>  CDBVariant::m_fltVal  
 Сохраняет значение типа **float**.  
  
### <a name="remarks"></a>Примечания  
 **M_fltVal** элемент данных относится к объединению. Перед обращением к **m_fltVal**, сначала проверьте значение [CDBVariant::m_dwType](#m_dwtype). Если `m_dwType` равно **DBVT_SINGLE**, затем **m_fltVal** содержит допустимое значение; в противном случае доступ к **m_fltVal** приведет к недостоверным результатам.  
  
##  <a name="m_ival"></a>  CDBVariant::m_iVal  
 Сохраняет значение типа **короткие**.  
  
### <a name="remarks"></a>Примечания  
 **M_iVal** элемент данных относится к объединению. Перед обращением к **m_iVal**, сначала проверьте значение [CDBVariant::m_dwType](#m_dwtype). Если `m_dwType` равно **DBVT_SHORT**, затем **m_iVal** содержит допустимое значение; в противном случае доступ к **m_iVal** приведет к недостоверным результатам.  
  
##  <a name="m_lval"></a>  CDBVariant::m_lVal  
 Сохраняет значение типа **длинные**.  
  
### <a name="remarks"></a>Примечания  
 **M_lVal** элемент данных относится к объединению. Перед обращением к **m_lVal**, сначала проверьте значение [CDBVariant::m_dwType](#m_dwtype). Если `m_dwType` равно **DBVT_LONG**, затем **m_lVal** содержит допустимое значение; в противном случае доступ к **m_lVal** приведет к недостоверным результатам.  
  
##  <a name="m_pbinary"></a>  CDBVariant::m_pbinary  
 Содержит указатель на объект типа [CLongBinary](../../mfc/reference/clongbinary-class.md).  
  
### <a name="remarks"></a>Примечания  
 **M_pbinary** элемент данных относится к объединению. Перед обращением к **m_pbinary**, сначала проверьте значение [CDBVariant::m_dwType](#m_dwtype). Если `m_dwType` равно **DBVT_BINARY**, затем **m_pbinary** содержит допустимый указатель; в противном случае доступ к **m_pbinary** приведет к недостоверным результатам.  
  
##  <a name="m_pdate"></a>  CDBVariant::m_pdate  
 Содержит указатель на объект типа **TIMESTAMP_STRUCT**.  
  
### <a name="remarks"></a>Примечания  
 **M_pdate** элемент данных относится к объединению. Перед обращением к **m_pdate**, сначала проверьте значение [CDBVariant::m_dwType](#m_dwtype). Если `m_dwType` равно **DBVT_DATE**, затем **m_pdate** содержит допустимый указатель; в противном случае доступ к **m_pdate** приведет к недостоверным результатам.  
  
 Дополнительные сведения о **TIMESTAMP_STRUCT** тип данных, см. в разделе [типы данных C](https://msdn.microsoft.com/library/ms714556.aspx) в приложении D *справочнике программиста ODBC* в Windows SDK.  
  
##  <a name="m_pstring"></a>  CDBVariant::m_pstring  
 Содержит указатель на объект типа [CString](../../atl-mfc-shared/reference/cstringt-class.md).  
  
### <a name="remarks"></a>Примечания  
 **M_pstring** элемент данных относится к объединению. Перед обращением к **m_pstring**, сначала проверьте значение [CDBVariant::m_dwType](#m_dwtype). Если `m_dwType` равно **DBVT_STRING**, затем **m_pstring** содержит допустимый указатель; в противном случае доступ к **m_pstring** приведет к недостоверным результатам.  
  
##  <a name="m_pstringa"></a>  CDBVariant::m_pstringA  
 Содержит указатель на ASCII [CString](../../atl-mfc-shared/reference/cstringt-class.md) объекта.  
  
### <a name="remarks"></a>Примечания  
 **M_pstringA** элемент данных относится к объединению. Перед обращением к **m_pstringA**, сначала проверьте значение [CDBVariant::m_dwType](#m_dwtype). Если `m_dwType` равно **DBVT_ASTRING**, затем **m_pstringA** содержит допустимый указатель; в противном случае доступ к **m_pstringA** приведет к недостоверным результатам.  
  
##  <a name="m_pstringw"></a>  CDBVariant::m_pstringW  
 Содержит указатель на уровне [CString](../../atl-mfc-shared/reference/cstringt-class.md) объекта.  
  
### <a name="remarks"></a>Примечания  
 **M_pstringW** элемент данных относится к объединению. Перед обращением к **m_pstringW**, сначала проверьте значение [CDBVariant::m_dwType](#m_dwtype). Если `m_dwType` равно **DBVT_WSTRING**, затем **m_pstringW** содержит допустимый указатель; в противном случае доступ к **m_pstringW** приведет к недостоверным результатам.  
  
## <a name="see-also"></a>См. также  
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Класс CRecordset](../../mfc/reference/crecordset-class.md)
