---
title: "Функции обмена данными диалоговых окнах для CRecordView и CDaoRecordView | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- AFXDAO/DDX_FieldCBIndex
- AFXDAO/DDX_FieldCBString
- AFXDAO/DDX_FieldCBStringExact
- AFXDAO/DDX_FieldCheck
- AFXDAO/DDX_FieldLBIndex
- AFXDAO/DDX_FieldLBString
- AFXDAO/DDX_FieldLBStringExact
- AFXDAO/DDX_FieldRadio
- AFXDAO/DDX_FieldScroll
- AFXDAO/DDX_FieldText
dev_langs:
- C++
helpviewer_keywords:
- DDX_Field functions [MFC]
- ODBC [MFC], dialog data exchange (DDX) support
- DDX (dialog data exchange) [MFC], database support
- DDX (dialog data exchange) [MFC], functions
- databases [MFC], dialog data exchange (DDX) support
- DAO [MFC], dialog data exchange (DDX) support
ms.assetid: 0d8cde38-3a2c-4100-9589-ac80a7b1ce91
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: f58b7ba7ae51c4db065cd7b30cc233128f7b7c68
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="dialog-data-exchange-functions-for-crecordview-and-cdaorecordview"></a>Функции обмена данными в диалоговых окнах для CRecordView и CDaoRecordView
В этом разделе перечислены DDX_Field-функции, используемые для обмена данными между [CRecordset](../../mfc/reference/crecordset-class.md) и [CRecordView](../../mfc/reference/crecordview-class.md) формы или [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md) и [ CDaoRecordView](../../mfc/reference/cdaorecordview-class.md) формы.  
  
> [!NOTE]
>  DDX_Field-функции похожи на функции DDX в том, что они обмениваются данными с элементами управления в форме. Но в отличие от DDX, обмена данными с полями представления ассоциированным объектом набора записей, а не с полями записи самого представления. Дополнительные сведения см. в разделе классы `CRecordView` и `CDaoRecordView`.  
  
### <a name="ddxfield-functions"></a>DDX_Field-функции  
  
|||  
|-|-|  
|[DDX_FieldCBIndex](#ddx_fieldcbindex)|Передает целочисленные данные между элементом данных полей набора записей и индекс текущего выделенного фрагмента в поле со списком в [CRecordView](../../mfc/reference/crecordview-class.md) или [CDaoRecordView](../../mfc/reference/cdaorecordview-class.md).|  
|[DDX_FieldCBString](#ddx_fieldcbstring)|Передача `CString` поле данных между элементом набора записей поля данных и поле редактирования поля со списком `CRecordView` или `CDaoRecordView`. При перемещении данных из набора записей в элемент управления, эта функция выбирает элемент в поле со списком, который начинается с символов в указанной строке.|  
|[DDX_FieldCBStringExact](#ddx_fieldcbstringexact)|Передача `CString` поле данных между элементом набора записей поля данных и поле редактирования поля со списком `CRecordView` или `CDaoRecordView`. При перемещении данных из набора записей в элемент управления, эта функция выбирает элемент в поле со списком, полностью совпадающий с указанной строкой.|  
|[DDX_FieldCheck](#ddx_fieldcheck)|Передает логический тип данных между элементом данных поле recordset и флажок в `CRecordView` или `CDaoRecordView`.|  
|[DDX_FieldLBIndex](#ddx_fieldlbindex)|Передает целочисленные данные между элементом данных полей набора записей и индекс текущего выделенного фрагмента в поле со списком в `CRecordView` или `CDaoRecordView`.|  
|[DDX_FieldLBString](#ddx_fieldlbstring)|Управляет передачей [CString](../../atl-mfc-shared/reference/cstringt-class.md) данных между элементами данных полей набора записей и управления списков. При перемещении данных из набора записей в элемент управления, эта функция выбирает элемент в списке, которая начинается с символов в указанной строке.|  
|[DDX_FieldLBStringExact](#ddx_fieldlbstringexact)|Управляет передачей `CString` данных между элементами данных полей набора записей и управления списков. При перемещении данных из набора записей в элемент управления, эта функция выбирает первый элемент, полностью совпадающий с указанной строкой.|  
|[DDX_FieldRadio](#ddx_fieldradio)|Передает целочисленные данные между элементом набора записей поля данных и группа переключателей в `CRecordView` или `CDaoRecordView`.|  
|[DDX_FieldScroll](#ddx_fieldscroll)|Задает или возвращает позицию прокрутки полосы прокрутки в `CRecordView` или `CDaoRecordView`. Вызов из вашего [DoFieldExchange](../../mfc/reference/cdaorecordset-class.md#dofieldexchange) функции.|  
|[DDX_FieldSlider](#ddx_fieldslider)|Синхронизирует положение бегунка элемента управления "ползунок" в представлении записей и `int` элемента данных поля в наборе записей. |
|[DDX_FieldText](#ddx_fieldtext)|Перегруженные версии доступны для переноса `int`, **UINT**, **длинные**, `DWORD`, [CString](../../atl-mfc-shared/reference/cstringt-class.md), **float** , **двойные**, **короткие**, [COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md), и [COleCurrency](../../mfc/reference/colecurrency-class.md) данных между элементом данных полей набора записей и изменения поле `CRecordView` или `CDaoRecordView`.|  
  
##  <a name="ddx_fieldcbindex"></a>DDX_FieldCBIndex  
 `DDX_FieldCBIndex` Функция синхронизирует индекс выбранного элемента в элементе списка элемента управления полем со списком в представлении записей и `int` элемента данных поля в наборе записей, связанный с представлением записи.  
  
```  
void AFXAPI DDX_FieldCBIndex(
    CDataExchange* pDX,    
    int nIDC,   
    int& index,  
    CRecordset* pRecordset);

void AFXAPI DDX_FieldCBIndex(
    CDataExchange* pDX,    
    int nIDC,   
    int& index,  
    CDaoRecordset* pRecordset);  
```  
  
### <a name="parameters"></a>Параметры  
 `pDX`  
 Указатель на [CDataExchange](../../mfc/reference/cdataexchange-class.md) объекта. Структура предоставляет этот объект для формирования контекста обмена данными, включая его направление.  
  
 `nIDC`  
 Идентификатор элемента управления в [CRecordView](../../mfc/reference/crecordview-class.md) или [CDaoRecordView](../../mfc/reference/cdaorecordview-class.md) объекта.  
  
 *Индекс*  
 Ссылка для элемента данных поля в связанном `CRecordset` или `CDaoRecordset` объекта.  
  
 `pRecordset`  
 Указатель на [CRecordset](../../mfc/reference/crecordset-class.md) или [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md) объекта при обмене данными.  
  
### <a name="remarks"></a>Примечания  
 При перемещении данных из набора записей в элемент управления, эта функция задает выбор в элементе управления, основываясь на значении, заданном в *индекса*. При перемещении из набора записей с элементом управления Если поле recordset имеет значение Null, MFC задает значение индекса 0. Для передачи управления в набор записей Если элемент управления является пустым или если элемент не выбран, поле recordset имеет значение 0.  
  
 Первая версия следует используйте при работе с классами на основе ODBC. При работе с помощью классов на основе DAO, используйте второй версии.  
  
 Дополнительные сведения об DDX см. в разделе [обмен данными диалоговых окон и проверка](../../mfc/dialog-data-exchange-and-validation.md). Примеры и Дополнительные сведения об ОБМЕНЕ для [CRecordView](../../mfc/reference/crecordview-class.md) и [CDaoRecordView](../../mfc/reference/cdaorecordview-class.md) поля, см. в статье [представления записей](../../data/record-views-mfc-data-access.md).  
  
### <a name="example"></a>Пример  
 В разделе [DDX_FieldText](#ddx_fieldtext) общие DDX_Field пример. Пример будет выглядеть для `DDX_FieldCBIndex`.  

### <a name="requirements"></a>Требования  
 **Заголовок:** afxdao.h  

##  <a name="ddx_fieldcbstring"></a>DDX_FieldCBString  
 `DDX_FieldCBString` Функция управляет передачей [CString](../../atl-mfc-shared/reference/cstringt-class.md) данных между поле редактирования поле со списком в представлении записей и `CString` элемента данных поля в наборе записей, связанный с представлением записи.  
  
```  
void AFXAPI DDX_FieldCBString(
    CDataExchange* pDX,    
    int nIDC,   
    CString& value,   
    CRecordset* pRecordset);

void AFXAPI DDX_FieldCBString(
    CDataExchange* pDX,    
    int nIDC,   
    CString& value,   
    CDaoRecordset* pRecordset);  
```  
  
### <a name="parameters"></a>Параметры  
 `pDX`  
 Указатель на [CDataExchange](../../mfc/reference/cdataexchange-class.md) объекта. Структура предоставляет этот объект для формирования контекста обмена данными, включая его направление.  
  
 `nIDC`  
 Идентификатор элемента управления в [CRecordView](../../mfc/reference/crecordview-class.md) или [CDaoRecordView](../../mfc/reference/cdaorecordview-class.md) объекта.  
  
 *значение*  
 Ссылка для элемента данных поля в связанном `CRecordset` или `CDaoRecordset` объекта.  
  
 `pRecordset`  
 Указатель на [CRecordset](../../mfc/reference/crecordset-class.md) или [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md) объекта при обмене данными.  
  
### <a name="remarks"></a>Примечания  
 При перемещении данных из набора записей в элемент управления, эта функция задает текущее выделение в поле со списком в первую строку, которая начинается с символов в строку, указанную в *значение*. При перемещении из набора записей с элементом управления, если поле recordset имеет значение Null, удаляются все параметры, выбранные из поле со списком, и поле редактирования комбинированного окна устанавливается на пустой. На передачу управления в набор записей Если элемент управления является пустым, поле recordset будет равно Null, если поле допускает.  
  
 Первая версия следует используйте при работе с классами на основе ODBC. При работе с помощью классов на основе DAO, используйте второй версии.  
  
 Дополнительные сведения об DDX см. в разделе [обмен данными диалоговых окон и проверка](../../mfc/dialog-data-exchange-and-validation.md). Примеры и Дополнительные сведения об ОБМЕНЕ для [CRecordView](../../mfc/reference/crecordview-class.md) и [CDaoRecordView](../../mfc/reference/cdaorecordview-class.md) поля, см. в статье [представления записей](../../data/record-views-mfc-data-access.md).  
  
### <a name="example"></a>Пример  
 В разделе [DDX_FieldText](#ddx_fieldtext) общие DDX_Field пример. Пример включает вызов `DDX_FieldCBString`.  
  
### <a name="requirements"></a>Требования  
  **Заголовок** afxdao.h  
  
## <a name="ddx_fieldcbstringexact"></a>DDX_FieldCBStringExact  
 `DDX_FieldCBStringExact` Функция управляет передачей [CString](../../atl-mfc-shared/reference/cstringt-class.md) данных между поле редактирования поле со списком в представлении записей и `CString` элемента данных поля в наборе записей, связанный с представлением записи.  
  
```  
void AFXAPI DDX_FieldCBStringExact(
    CDataExchange* pDX,    
    int nIDC,   
    CString& value,   
    CRecordset* pRecordset);

void AFXAPI DDX_FieldCBStringExact(
    CDataExchange* pDX,    
    int nIDC,   
    CString& value,   
    CDaoRecordset* pRecordset);  
```  
  
### <a name="parameters"></a>Параметры  
 `pDX`  
 Указатель на [CDataExchange](../../mfc/reference/cdataexchange-class.md) объекта. Структура предоставляет этот объект для формирования контекста обмена данными, включая его направление.  
  
 `nIDC`  
 Идентификатор элемента управления в [CRecordView](../../mfc/reference/crecordview-class.md) или [CDaoRecordView](../../mfc/reference/cdaorecordview-class.md) объекта.  
  
 *значение*  
 Ссылка для элемента данных поля в связанном `CRecordset` или `CDaoRecordset` объекта.  
  
 `pRecordset`  
 Указатель на [CRecordset](../../mfc/reference/crecordset-class.md) или [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md) объекта при обмене данными.  
  
### <a name="remarks"></a>Примечания  
 При перемещении данных из набора записей в элемент управления, эта функция задает текущее выделение в поле со списком в первую строку, точно соответствующие строки, указанной в *значение*. При перемещении из набора записей с элементом управления, если поле recordset имеет значение NULL, удаляются все параметры, выбранные из поле со списком, и поле редактирования комбинированного окна устанавливается на пустой. Для передачи управления в набор записей Если элемент управления является пустым, поле recordset будет равно NULL.  
  
 Первая версия следует используйте при работе с классами на основе ODBC. При работе с помощью классов на основе DAO, используйте второй версии.  
  
 Дополнительные сведения об DDX см. в разделе [обмен данными диалоговых окон и проверка](../../mfc/dialog-data-exchange-and-validation.md). Примеры и Дополнительные сведения об ОБМЕНЕ для [CRecordView](../../mfc/reference/crecordview-class.md) и [CDaoRecordView](../../mfc/reference/cdaorecordview-class.md) поля, см. в статье [представления записей](../../data/record-views-mfc-data-access.md).  
  
### <a name="example"></a>Пример  
 В разделе [DDX_FieldText](#ddx_fieldtext) общие DDX_Field пример. Вызовы `DDX_FieldCBStringExact` должен выглядеть примерно так.  
  
### <a name="requirements"></a>Требования  
  **Заголовок** afxdao.h  
  
##  <a name="ddx_fieldcheck"></a>DDX_FieldCheck  
 `DDX_FieldCheck` Функция управляет передачей `int` данных между управления «флажок» в диалоговом окне, представлении формы или объекте представления элемента управления и `int` данными-членом диалоговое окно, представление формы или объекте представления элемента управления.  
  
```  
void AFXAPI DDX_FieldCheck(
    CDataExchange* pDX,    
    int nIDC,   
    int& value,   
    CRecordset* pRecordset);

void AFXAPI DDX_FieldCheck(
    CDataExchange* pDX,    
    int nIDC,   
    int& value,   
    CDaoRecordset* pRecordset);  
```  
  
### <a name="parameters"></a>Параметры  
 `pDX`  
 Указатель на [CDataExchange](../../mfc/reference/cdataexchange-class.md) объекта. Структура предоставляет этот объект для формирования контекста обмена данными, включая его направление.  
  
 `nIDC`  
 Идентификатор ресурса управления «флажок», связанное со свойством элемента управления.  
  
 *значение*  
 Ссылка на переменную-член диалогового, представление формы или объекте представления элемента управления при обмене данными.  
  
 `pRecordset`  
 Указатель на [CRecordset](../../mfc/reference/crecordset-class.md) или [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md) объекта при обмене данными.  
  
### <a name="remarks"></a>Примечания  
 При `DDX_FieldCheck` вызове *значение* присваивается текущее состояние элемента управления "флажок" или состояние элемента управления имеет значение *значение*, в зависимости от направления передачи.  
  
 Дополнительные сведения об DDX см. в разделе [обмен данными диалоговых окон и проверка](../../mfc/dialog-data-exchange-and-validation.md).  
  
### <a name="requirements"></a>Требования  
  **Заголовок** afxdao.h  
  
##  <a name="ddx_fieldlbindex"></a>DDX_FieldLBIndex  
 `DDX_FieldLBIndex` Функция синхронизирует индекс выбранного элемента в элемент управления списком в представлении записей и `int` элемента данных поля в наборе записей, связанный с представлением записи.  
  
```  
void AFXAPI DDX_FieldLBIndex(
    CDataExchange* pDX,    
    int nIDC,   
    int& index,  
    CRecordset* pRecordset);

void AFXAPI DDX_FieldLBIndex(
    CDataExchange* pDX,    
    int nIDC,   
    int& index,  
    CDaoRecordset* pRecordset);  
```  
  
### <a name="parameters"></a>Параметры  
 `pDX`  
 Указатель на [CDataExchange](../../mfc/reference/cdataexchange-class.md) объекта. Структура предоставляет этот объект для формирования контекста обмена данными, включая его направление.  
  
 `nIDC`  
 Идентификатор элемента управления в [CRecordView](../../mfc/reference/crecordview-class.md) или [CDaoRecordView](../../mfc/reference/cdaorecordview-class.md) объекта.  
  
 *Индекс*  
 Ссылка для элемента данных поля в связанном `CRecordset` или `CDaoRecordset` объекта.  
  
 `pRecordset`  
 Указатель на [CRecordset](../../mfc/reference/crecordset-class.md) или [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md) объекта при обмене данными.  
  
### <a name="remarks"></a>Примечания  
 При перемещении данных из набора записей в элемент управления, эта функция задает выбор в элементе управления, основываясь на значении, заданном в *индекса*. При перемещении из набора записей с элементом управления Если поле recordset имеет значение Null, MFC задает значение индекса 0. Для передачи управления в набор записей Если элемент управления является пустым, поле recordset имеет значение 0.  
  
 Первая версия следует используйте при работе с классами на основе ODBC. При работе с помощью классов на основе DAO, используйте второй версии.  
  
 Дополнительные сведения об DDX см. в разделе [обмен данными диалоговых окон и проверка](../../mfc/dialog-data-exchange-and-validation.md). Примеры и Дополнительные сведения об ОБМЕНЕ для [CRecordView](../../mfc/reference/crecordview-class.md) и [CDaoRecordView](../../mfc/reference/cdaorecordview-class.md) поля, см. в статье [представления записей](../../data/record-views-mfc-data-access.md).  
  
### <a name="example"></a>Пример  
 В разделе [DDX_FieldText](#ddx_fieldtext) общие DDX_Field пример.  
  
### <a name="requirements"></a>Требования  
  **Заголовок** afxdao.h  
  
##  <a name="ddx_fieldlbstring"></a>DDX_FieldLBString  
 `DDX_FieldLBString` Копирует текущее выделение списка элемента управления полем в представлении записей для [CString](../../atl-mfc-shared/reference/cstringt-class.md) элемента данных поля в наборе записей, связанный с представлением записи.  
  
```  
void AFXAPI DDX_FieldLBString(
    CDataExchange* pDX,    
    int nIDC,   
    CString& value,   
    CRecordset* pRecordset);

void AFXAPI DDX_FieldLBString(
    CDataExchange* pDX,    
    int nIDC,   
    CString& value,   
    CDaoRecordset* pRecordset);  
```  
  
### <a name="parameters"></a>Параметры  
 `pDX`  
 Указатель на [CDataExchange](../../mfc/reference/cdataexchange-class.md) объекта. Структура предоставляет этот объект для формирования контекста обмена данными, включая его направление.  
  
 `nIDC`  
 Идентификатор элемента управления в [CRecordView](../../mfc/reference/crecordview-class.md) или [CDaoRecordView](../../mfc/reference/cdaorecordview-class.md) объекта.  
  
 *значение*  
 Ссылка для элемента данных поля в связанном `CRecordset` или `CDaoRecordset` объекта.  
  
 `pRecordset`  
 Указатель на [CRecordset](../../mfc/reference/crecordset-class.md) или [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md) объекта при обмене данными.  
  
### <a name="remarks"></a>Примечания  
 В обратном направлении, эта функция задает текущее выделение в списке на первую строку, которая начинается с символов в строки, заданной параметром *значение*. При перемещении из набора записей с элементом управления Если поле recordset имеет значение Null, все параметры, выбранные удаляется поле со списком. Для передачи управления в набор записей Если элемент управления является пустым, поле recordset будет равно Null.  
  
 Первая версия следует используйте при работе с классами на основе ODBC. При работе с помощью классов на основе DAO, используйте второй версии.  
  
 Дополнительные сведения об DDX см. в разделе [обмен данными диалоговых окон и проверка](../../mfc/dialog-data-exchange-and-validation.md). Примеры и Дополнительные сведения об ОБМЕНЕ для [CRecordView](../../mfc/reference/crecordview-class.md) и [CDaoRecordView](../../mfc/reference/cdaorecordview-class.md) поля, см. в статье [представления записей](../../data/record-views-mfc-data-access.md).  
  
### <a name="example"></a>Пример  
 В разделе [DDX_FieldText](#ddx_fieldtext) общие DDX_Field пример. Вызовы `DDX_FieldLBString` должен выглядеть примерно так.  
  
### <a name="requirements"></a>Требования  
  **Заголовок** afxdao.h  
  
##  <a name="ddx_fieldlbstringexact"></a>DDX_FieldLBStringExact  
 `DDX_FieldLBStringExact` Функция копирует текущее выделение списка элемента управления полем в представлении записей для [CString](../../atl-mfc-shared/reference/cstringt-class.md) элемента данных поля в наборе записей, связанный с представлением записи.  
  
```  
void AFXAPI DDX_FieldLBStringExact(
    CDataExchange* pDX,    
    int nIDC,   
    CString& value,   
    CRecordset* pRecordset);

void AFXAPI DDX_FieldLBStringExact(
    CDataExchange* pDX,    
    int nIDC,   
    CString& value,   
    CDaoRecordset* pRecordset);  
```  
  
### <a name="parameters"></a>Параметры  
 `pDX`  
 Указатель на [CDataExchange](../../mfc/reference/cdataexchange-class.md) объекта. Структура предоставляет этот объект для формирования контекста обмена данными, включая его направление.  
  
 `nIDC`  
 Идентификатор элемента управления в [CRecordView](../../mfc/reference/crecordview-class.md) или [CDaoRecordView](../../mfc/reference/cdaorecordview-class.md) объекта.  
  
 *значение*  
 Ссылка для элемента данных поля в связанном `CRecordset` или `CDaoRecordset` объекта.  
  
 `pRecordset`  
 Указатель на [CRecordset](../../mfc/reference/crecordset-class.md) или [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md) объекта при обмене данными.  
  
### <a name="remarks"></a>Примечания  
 В обратном направлении, эта функция задает текущее выделение в раскрывающемся списке первой строки, точно соответствующие строки, указанной в *значение*. При перемещении из набора записей с элементом управления Если поле recordset имеет значение Null, все параметры, выбранные удаляется поле со списком. Для передачи управления в набор записей Если элемент управления является пустым, поле recordset будет равно Null.  
  
 Первая версия следует используйте при работе с классами на основе ODBC. При работе с помощью классов на основе DAO, используйте второй версии.  
  
 Дополнительные сведения об DDX см. в разделе [обмен данными диалоговых окон и проверка](../../mfc/dialog-data-exchange-and-validation.md). Примеры и Дополнительные сведения об ОБМЕНЕ для [CRecordView](../../mfc/reference/crecordview-class.md) и [CDaoRecordView](../../mfc/reference/cdaorecordview-class.md) поля, см. в статье [представления записей](../../data/record-views-mfc-data-access.md).  
  
### <a name="example"></a>Пример  
 В разделе [DDX_FieldText](#ddx_fieldtext) общие DDX_Field пример. Вызовы `DDX_FieldLBStringExact` должен выглядеть примерно так.  
  
### <a name="requirements"></a>Требования  
  **Заголовок** afxdao.h  
  
##  <a name="ddx_fieldradio"></a>DDX_FieldRadio  
 `DDX_FieldRadio` Функция связывает начинающийся с нуля `int` переменной-члена записей представления записей с выбранного переключателя в группе переключателей в представлении записей.  
  
```  
void AFXAPI DDX_FieldRadio(
    CDataExchange* pDX,    
    int nIDC,   
    int& value,   
    CRecordset* pRecordset);

void AFXAPI DDX_FieldRadio(
    CDataExchange* pDX,    
    int nIDC,   
    int& value,   
    CDaoRecordset* pRecordset);  
```  
  
### <a name="parameters"></a>Параметры  
 `pDX`  
 Указатель на [CDataExchange](../../mfc/reference/cdataexchange-class.md) объекта. Структура предоставляет этот объект для формирования контекста обмена данными, включая его направление.  
  
 `nIDC`  
 Идентификатор первого в группе (стилем **WS_GROUP**) смежные переключателей в [CRecordView](../../mfc/reference/crecordview-class.md) или [CDaoRecordView](../../mfc/reference/cdaorecordview-class.md) объекта.  
  
 *значение*  
 Ссылка для элемента данных поля в связанном `CRecordset` или `CDaoRecordset` объекта.  
  
 `pRecordset`  
 Указатель на [CRecordset](../../mfc/reference/crecordset-class.md) или [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md) объекта при обмене данными.  
  
### <a name="remarks"></a>Примечания  
 При передаче из поля набора записей в представлении, эта функция включает *n-й* переключатель (от нуля), а также отключает другие кнопки. В обратном направлении эта функция устанавливает для поля набора записей с порядковым номером переключателя, который включен в данный момент (флажок установлен). При перемещении из набора записей с элементом управления Если поле recordset имеет значение Null, не выбран. Для передачи управления в набор записей Если элемент управления не установлен, поле recordset будет равно Null, если поле допускает.  
  
 Первая версия следует используйте при работе с классами на основе ODBC. При работе с помощью классов на основе DAO, используйте второй версии.  
  
 Дополнительные сведения об DDX см. в разделе [обмен данными диалоговых окон и проверка](../../mfc/dialog-data-exchange-and-validation.md). Примеры и Дополнительные сведения об ОБМЕНЕ для [CRecordView](../../mfc/reference/crecordview-class.md) и [CDaoRecordView](../../mfc/reference/cdaorecordview-class.md) поля, см. в статье [представления записей](../../data/record-views-mfc-data-access.md).  
  
### <a name="example"></a>Пример  
 В разделе [DDX_FieldText](#ddx_fieldtext) общие DDX_Field пример. Вызовы `DDX_FieldRadio` должен выглядеть примерно так.  
  
### <a name="requirements"></a>Требования  
  **Заголовок** afxdao.h  
  
##  <a name="ddx_fieldscroll"></a>DDX_FieldScroll  
 `DDX_FieldScroll` Функция синхронизирует позицию прокрутки полосы прокрутки в представлении записей и `int` элемента данных поля в наборе записей, связанные с представления записей (или любые целочисленной переменной, необходимо сопоставить его с).  
  
```  
void AFXAPI DDX_FieldScroll(
    CDataExchange* pDX,    
    int nIDC,   
    int& value,   
    CRecordset* pRecordset);

void AFXAPI DDX_FieldScroll(
    CDataExchange* pDX,    
    int nIDC,   
    int& value,   
    CDaoRecordset* pRecordset);  
```  
  
### <a name="parameters"></a>Параметры  
 `pDX`  
 Указатель на [CDataExchange](../../mfc/reference/cdataexchange-class.md) объекта. Структура предоставляет этот объект для формирования контекста обмена данными, включая его направление.  
  
 *nIDC\**  
 Идентификатор первого в группе (стилем **WS_GROUP**) смежные переключателей в [CRecordView](../../mfc/reference/crecordview-class.md) или [CDaoRecordView](../../mfc/reference/cdaorecordview-class.md) объекта.  
  
 *значение*  
 Ссылка для элемента данных поля в связанном `CRecordset` или `CDaoRecordset` объекта.  
  
 `pRecordset`  
 Указатель на [CRecordset](../../mfc/reference/crecordset-class.md) или [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md) объекта при обмене данными.  
  
### <a name="remarks"></a>Примечания  
 При перемещении данных из набора записей в элемент управления, эта функция задает позицию прокрутки полосы прокрутки к значению, указанному в *значение*. При перемещении из набора записей с элементом управления Если поле recordset имеет значение Null, полосы прокрутки имеет значение 0. Для передачи управления в набор записей Если элемент управления не указано, значение поля набора записей — 0.  
  
 Первая версия следует используйте при работе с классами на основе ODBC. При работе с помощью классов на основе DAO, используйте второй версии.  
  
 Дополнительные сведения об DDX см. в разделе [обмен данными диалоговых окон и проверка](../../mfc/dialog-data-exchange-and-validation.md). Примеры и Дополнительные сведения об ОБМЕНЕ для [CRecordView](../../mfc/reference/crecordview-class.md) и [CDaoRecordView](../../mfc/reference/cdaorecordview-class.md) поля, см. в статье [представления записей](../../data/record-views-mfc-data-access.md).  
  
### <a name="example"></a>Пример  
 В разделе [DDX_FieldText](#ddx_fieldtext) общие DDX_Field пример. Вызовы `DDX_FieldScroll` должен выглядеть примерно так.  
  
### <a name="requirements"></a>Требования  
  **Заголовок** afxdao.h  

  ## <a name="nameddxfieldslidera--ddxfieldslider"></a>Имя = «ddx_fieldslider» ></a> DDX_FieldSlider
`DDX_FieldSlider` Функция синхронизирует положение бегунка элемента управления "ползунок" в представлении записей и `int` элемента данных поля в наборе записей, связанные с представления записей (или любые целочисленной переменной, необходимо сопоставить его с).  
   
### <a name="syntax"></a>Синтаксис  
  ```
   void AFXAPI DDX_FieldSlider(  
       CDataExchange* pDX,  
       int nIDC,  
       int& value,  
       CRecordset* pRecordset );  

void AFXAPI DDX_FieldSlider(  
     CDataExchange* pDX,  
     int nIDC,  
     int& value,  
     CDaoRecordset* pRecordset );  
```
### <a name="parameters"></a>Параметры  
 `pDX`  
 Указатель на [CDataExchange](cdataexchange-class.md) объекта. Структура предоставляет этот объект для формирования контекста обмена данными, включая его направление.  
  
 `nIDC`  
 Идентификатор ресурса управления "ползунок".  
  
 *значение*  
 Ссылка на значение для обмена. Этот параметр содержит или будет использоваться для задания элемента управления "ползунок" текущее положение бегунка.  
  
 `pRecordset`  
 Указатель на связанный `CRecordset` или `CDaoRecordset` объекта при обмене данными.  
   
### <a name="remarks"></a>Примечания  
 При перемещении данных из набора записей ползунок, эта функция задает значение, указанное в положение движка *значение*. При перемещении из набора записей с элементом управления Если поле recordset имеет значение Null, положение элемента управления "ползунок" равен 0. При перемещении элемента управления в набор записей Если элемент управления не указано, значение поля набора записей — 0.  
  
 `DDX_FieldSlider`не обмениваются информацией о диапазона с элементами управления "ползунок" поддерживает параметр диапазона, а не просто позиции.  
  
 Первый переопределение функции следует используйте при работе с классами на основе ODBC. Используйте второй переопределения с помощью классов на основе DAO.  
  
 Дополнительные сведения об DDX см. в разделе [обмен данными диалоговых окон и проверка](../dialog-data-exchange-and-validation.md). Примеры и Дополнительные сведения об ОБМЕНЕ для `CRecordView` и `CDaoRecordView` поля, в разделе [представления записей](../../data/record-views-mfc-data-access.md). Сведения об элементах управления "ползунок" в разделе [использование CSliderCtrl](../using-csliderctrl.md).  
   
### <a name="example"></a>Пример  
 В разделе [DDX_FieldText](#ddx_fieldtext) общие DDX_Field пример. Вызовы `DDX_FieldSlider` должен выглядеть примерно так.  
   
### <a name="requirements"></a>Требования  
 **Заголовок:** afxdao.h  
   
### <a name="see-also"></a>См. также  
 [Макросы и глобальные объекты](mfc-macros-and-globals.md)   
  
##  <a name="ddx_fieldtext"></a>DDX_FieldText  
 `DDX_FieldText` Функция управляет передачей `int`, **короткие**, **длинные**, `DWORD`, [CString](../../atl-mfc-shared/reference/cstringt-class.md), **float**, **двойные**, **BOOL**, или **БАЙТОВ** данных между поля ввода и элементами данных полей в наборе записей.  
  
```  
void AFXAPI DDX_FieldText(
    CDataExchange* pDX,    
    int nIDC,   
    BYTE& value,   
    CRecordset* pRecordset);

void AFXAPI DDX_FieldText(
    CDataExchange* pDX,    
    int nIDC,   
    int& value,   
    CRecordset* pRecordset);

void AFXAPI DDX_FieldText(
    CDataExchange* pDX,    
    int nIDC,   
    UINT& value,   
    CRecordset* pRecordset);

void AFXAPI DDX_FieldText(
    CDataExchange* pDX,    
    int nIDC,   
    long& value,   
    CRecordset* pRecordset);

void AFXAPI DDX_FieldText(
    CDataExchange* pDX,    
    int nIDC,   
    DWORD& value,   
    CRecordset* pRecordset);

void AFXAPI DDX_FieldText(
    CDataExchange* pDX,    
    int nIDC,   
    CString& value,   
    CRecordset* pRecordset);

void AFXAPI DDX_FieldText(
    CDataExchange* pDX,    
    int nIDC,   
    float& value,   
    CRecordset* pRecordset);

void AFXAPI DDX_FieldText(
    CDataExchange* pDX,    
    int nIDC,   
    double& value,   
    CRecordset* pRecordset);

void AFXAPI DDX_FieldText(
    CDataExchange* pDX,    
    int nIDC,   
    short& value,   
    CDaoRecordset* pRecordset);

void AFXAPI DDX_FieldText(
    CDataExchange* pDX,    
    int nIDC,   
    BOOL& value,   
    CDaoRecordset* pRecordset);

void AFXAPI DDX_FieldText(
    CDataExchange* pDX,    
    int nIDC,   
    BYTE& value,   
    CDaoRecordset* pRecordset);

void AFXAPI DDX_FieldText(
    CDataExchange* pDX,    
    int nIDC,   
    long& value,   
    CDaoRecordset* pRecordset);

void AFXAPI DDX_FieldText(
    CDataExchange* pDX,    
    int nIDC,   
    DWORD& value,   
    CDaoRecordset* pRecordset);

void AFXAPI DDX_FieldText(
    CDataExchange* pDX,    
    int nIDC,   
    CString& value,   
    CDaoRecordset* pRecordset);

void AFXAPI DDX_FieldText(
    CDataExchange* pDX,    
    int nIDC,   
    float& value,   
    CDaoRecordset* pRecordset);

void AFXAPI DDX_FieldText(
    CDataExchange* pDX,    
    int nIDC,   
    double& value,   
    CDaoRecordset* pRecordset);

void AFXAPI DDX_FieldText(
    CDataExchange* pDX,    
    int nIDC,   
    COleDateTime& value,   
    CDaoRecordset* pRecordset);

void AFXAPI DDX_FieldText(
    CDataExchange* pDX,    
    int nIDC,   
    COleCurrency& value,   
    CDaoRecordset* pRecordset);  
```  
  
### <a name="parameters"></a>Параметры  
 `pDX`  
 Указатель на [CDataExchange](../../mfc/reference/cdataexchange-class.md) объекта. Структура предоставляет этот объект для формирования контекста обмена данными, включая его направление.  
  
 `nIDC`  
 Идентификатор элемента управления в [CRecordView](../../mfc/reference/crecordview-class.md) или [CDaoRecordView](../../mfc/reference/cdaorecordview-class.md) объекта.  
  
 *значение*  
 Ссылка для элемента данных поля в связанном `CRecordset` или `CDaoRecordset` объекта. Тип данных значения зависит от какой из перегруженных версий `DDX_FieldText` используется.  
  
 `pRecordset`  
 Указатель на [CRecordset](../../mfc/reference/crecordset-class.md) или [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md) объекта при обмене данными. Этот указатель позволяет `DDX_FieldText` для обнаружения и установки значений Null.  
  
### <a name="remarks"></a>Примечания  
 Для [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md) объектов, `DDX_FieldText` также управляет передачи [COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md), и [COleCurrency](../../mfc/reference/colecurrency-class.md) значения. Поле ввода пустым указывает значение Null. За передачу набора записей с элементом управления, если поле recordset имеет значение Null, устанавливается поле ввода пустым. Для передачи управления в набор записей Если элемент управления является пустым, поле recordset будет равно Null.  
  
 Использование версии с [CRecordset](../../mfc/reference/crecordset-class.md) параметры при работе с классами на основе ODBC. Использование версии с [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md) параметры при работе с помощью классов на основе DAO.  
  
 Дополнительные сведения об DDX см. в разделе [обмен данными диалоговых окон и проверка](../../mfc/dialog-data-exchange-and-validation.md). Примеры и Дополнительные сведения об ОБМЕНЕ для [CRecordView](../../mfc/reference/crecordview-class.md) и [CDaoRecordView](../../mfc/reference/cdaorecordview-class.md) поля, см. в статье [представления записей](../../data/record-views-mfc-data-access.md).  
  
### <a name="example"></a>Пример  
 Следующие `DoDataExchange` функции для [CRecordView](../../mfc/reference/crecordview-class.md) содержит `DDX_FieldText` функция вызывает для трех типов данных: `IDC_COURSELIST` является списком; другие два элемента управления, поля ввода. Для программирования DAO *m_pSet* — указатель на [CRecordset](../../mfc/reference/crecordset-class.md) или [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md).  
  
 [!code-cpp[NVC_MFCDatabase#43](../../mfc/codesnippet/cpp/dialog-data-exchange-functions-for-crecordview-and-cdaorecordview_1.cpp)]  

  
### <a name="requirements"></a>Требования  
  **Заголовок** afxdao.h  
    
## <a name="see-also"></a>См. также  
 [Макросы и глобальные объекты](../../mfc/reference/mfc-macros-and-globals.md)
