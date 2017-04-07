---
title: "CDBVariant-класс | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
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
- CDBVariant class
- Variant data types, ODBC
ms.assetid: de23609c-c560-4b24-bd6b-9d8903fd5b49
caps.latest.revision: 21
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
ms.sourcegitcommit: 040985df34f2613b4e4fae29498721aef15d50cb
ms.openlocfilehash: 930115ce4fe673e82a447ab1d90c260fe2b941d6
ms.lasthandoff: 02/24/2017

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
|[CDBVariant::m_dwType](#m_dwtype)|Содержит тип данных в настоящее время сохраненное значение. Введите `DWORD`.|  
  
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
|[CDBVariant::m_pstringA](#m_pstringa)|Хранит указатель ASCII [CString](../../atl-mfc-shared/reference/cstringt-class.md) объекта.|  
|[CDBVariant::m_pstringW](#m_pstringw)|Хранит указатель на уровне [CString](../../atl-mfc-shared/reference/cstringt-class.md) объекта.|  
  
## <a name="remarks"></a>Примечания  
 `CDBVariant`не имеет базового класса.  
  
 `CDBVariant`Аналогично [COleVariant](../../mfc/reference/colevariant-class.md), однако `CDBVariant` не использует OLE. `CDBVariant`позволяет хранить значения, не беспокоясь о типами данных. `CDBVariant`отслеживает текущее значение, которое хранится в объединении тип данных.  
  
 Класс [CRecordset](../../mfc/reference/crecordset-class.md) использует `CDBVariant` объектов в трех функций-членов: `GetFieldValue`, `GetBookmark`, и `SetBookmark`. Например `GetFieldValue` позволяет динамически извлекать данные в столбце. Поскольку тип данных столбца не может быть известен во время выполнения `GetFieldValue` использует `CDBVariant` объект для хранения данных столбца.  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 `CDBVariant`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxdb.h  
  
##  <a name="cdbvariant"></a>CDBVariant::CDBVariant  
 Создает значение NULL `CDBVariant` объекта.  
  
```  
CDBVariant();
```  
  
### <a name="remarks"></a>Примечания  
 Наборы [m_dwType](#m_dwtype) член данных **DBVT_NULL**.  
  
##  <a name="clear"></a>CDBVariant::Clear  
 Вызовите эту функцию-член снимите `CDBVariant` объекта.  
  
```  
void Clear();
```  
  
### <a name="remarks"></a>Примечания  
 Если значение [m_dwType](#m_dwtype) данные-член **DBVT_DATE**, **DBVT_STRING**, или **DBVT_BINARY**, **снимите** освобождает память, связанная с элементом объединения указателя. **Очистить** задает `m_dwType` для **DBVT_NULL**.  
  
 `CDBVariant` Вызывает деструктор **снимите**.  
  
##  <a name="m_boolval"></a>CDBVariant::m_boolVal  
 Сохраняет значение с типом **BOOL**.  
  
### <a name="remarks"></a>Примечания  
 **M_boolVal** данные-член принадлежит к объединению. Перед обращением к **m_boolVal**, сначала проверьте значение [CDBVariant::m_dwType](#m_dwtype). Если `m_dwType` равен **DBVT_BOOL**, затем **m_boolVal** будет содержать допустимое значение; в противном случае — доступ к **m_boolVal** ненадежные результаты.  
  
##  <a name="m_chval"></a>CDBVariant::m_chVal  
 Сохраняет значение типа `unsigned char`.  
  
### <a name="remarks"></a>Примечания  
 **M_chVal** данные-член принадлежит к объединению. Перед обращением к **m_chVal**, сначала проверьте значение [CDBVariant::m_dwType](#m_dwtype). Если `m_dwType` равен **DBVT_UCHAR**, затем **m_chVal** содержит допустимое значение; в противном случае — доступ к **m_chVal** ненадежные результаты.  
  
##  <a name="m_dblval"></a>CDBVariant::m_dblVal  
 Сохраняет значение с типом **двойные**.  
  
### <a name="remarks"></a>Примечания  
 **M_dblVal** данные-член принадлежит к объединению. Перед обращением к **m_dblVal**, сначала проверьте значение [CDBVariant::m_dwType](#m_dwtype). Если `m_dwType` равен **DBVT_DOUBLE**, затем **m_dblVal** содержит допустимое значение; в противном случае — доступ к **m_dblVal** ненадежные результаты.  
  
##  <a name="m_dwtype"></a>CDBVariant::m_dwType  
 Этот элемент данных содержит тип данных для значения, хранящегося в `CDBVariant` члену объекта объединения данных.  
  
### <a name="remarks"></a>Примечания  
 Перед обращением к это объединение, необходимо проверить значение `m_dwType` , чтобы определить, какой элемент объединения данных для доступа к. В следующей таблице перечислены возможные значения для `m_dwType` и соответствующий элемент объединения данных.  
  
|m_dwType|Элемент объединения данных|  
|---------------|-----------------------|  
|**DBVT_NULL**|Члены объединений не является допустимым для доступа.|  
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
  
##  <a name="m_fltval"></a>CDBVariant::m_fltVal  
 Сохраняет значение с типом **float**.  
  
### <a name="remarks"></a>Примечания  
 **M_fltVal** данные-член принадлежит к объединению. Перед обращением к **m_fltVal**, сначала проверьте значение [CDBVariant::m_dwType](#m_dwtype). Если `m_dwType` равен **DBVT_SINGLE**, затем **m_fltVal** содержит допустимое значение; в противном случае — доступ к **m_fltVal** ненадежные результаты.  
  
##  <a name="m_ival"></a>CDBVariant::m_iVal  
 Сохраняет значение с типом **короткие**.  
  
### <a name="remarks"></a>Примечания  
 **M_iVal** данные-член принадлежит к объединению. Перед обращением к **m_iVal**, сначала проверьте значение [CDBVariant::m_dwType](#m_dwtype). Если `m_dwType` равен **DBVT_SHORT**, затем **m_iVal** содержит допустимое значение; в противном случае — доступ к **m_iVal** ненадежные результаты.  
  
##  <a name="m_lval"></a>CDBVariant::m_lVal  
 Сохраняет значение с типом **длинные**.  
  
### <a name="remarks"></a>Примечания  
 **M_lVal** данные-член принадлежит к объединению. Перед обращением к **m_lVal**, сначала проверьте значение [CDBVariant::m_dwType](#m_dwtype). Если `m_dwType` равен **DBVT_LONG**, затем **m_lVal** содержит допустимое значение; в противном случае — доступ к **m_lVal** ненадежные результаты.  
  
##  <a name="m_pbinary"></a>CDBVariant::m_pbinary  
 Содержит указатель на объект типа [CLongBinary](../../mfc/reference/clongbinary-class.md).  
  
### <a name="remarks"></a>Примечания  
 **M_pbinary** данные-член принадлежит к объединению. Перед обращением к **m_pbinary**, сначала проверьте значение [CDBVariant::m_dwType](#m_dwtype). Если `m_dwType` равен **DBVT_BINARY**, затем **m_pbinary** содержит допустимый указатель; в противном случае — доступ к **m_pbinary** ненадежные результаты.  
  
##  <a name="m_pdate"></a>CDBVariant::m_pdate  
 Содержит указатель на объект типа **TIMESTAMP_STRUCT**.  
  
### <a name="remarks"></a>Примечания  
 **M_pdate** данные-член принадлежит к объединению. Перед обращением к **m_pdate**, сначала проверьте значение [CDBVariant::m_dwType](#m_dwtype). Если `m_dwType` равен **DBVT_DATE**, затем **m_pdate** содержит допустимый указатель; в противном случае — доступ к **m_pdate** ненадежные результаты.  
  
 Дополнительные сведения о **TIMESTAMP_STRUCT** тип данных, см. в разделе [типы данных C](https://msdn.microsoft.com/library/ms714556.aspx) в приложении D *Справочник программиста по ODBC* в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="m_pstring"></a>CDBVariant::m_pstring  
 Содержит указатель на объект типа [CString](../../atl-mfc-shared/reference/cstringt-class.md).  
  
### <a name="remarks"></a>Примечания  
 **M_pstring** данные-член принадлежит к объединению. Перед обращением к **m_pstring**, сначала проверьте значение [CDBVariant::m_dwType](#m_dwtype). Если `m_dwType` равен **DBVT_STRING**, затем **m_pstring** содержит допустимый указатель; в противном случае — доступ к **m_pstring** ненадежные результаты.  
  
##  <a name="m_pstringa"></a>CDBVariant::m_pstringA  
 Хранит указатель ASCII [CString](../../atl-mfc-shared/reference/cstringt-class.md) объекта.  
  
### <a name="remarks"></a>Примечания  
 **M_pstringA** данные-член принадлежит к объединению. Перед обращением к **m_pstringA**, сначала проверьте значение [CDBVariant::m_dwType](#m_dwtype). Если `m_dwType` равен **DBVT_ASTRING**, затем **m_pstringA** содержит допустимый указатель; в противном случае — доступ к **m_pstringA** ненадежные результаты.  
  
##  <a name="m_pstringw"></a>CDBVariant::m_pstringW  
 Хранит указатель на уровне [CString](../../atl-mfc-shared/reference/cstringt-class.md) объекта.  
  
### <a name="remarks"></a>Примечания  
 **M_pstringW** данные-член принадлежит к объединению. Перед обращением к **m_pstringW**, сначала проверьте значение [CDBVariant::m_dwType](#m_dwtype). Если `m_dwType` равен **DBVT_WSTRING**, затем **m_pstringW** содержит допустимый указатель; в противном случае — доступ к **m_pstringW** ненадежные результаты.  
  
## <a name="see-also"></a>См. также  
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Класс CRecordset](../../mfc/reference/crecordset-class.md)

