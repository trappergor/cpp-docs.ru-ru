---
title: "Функции обмена данными диалоговых окнах для CRecordView и CDaoRecordView | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
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
- DDX_Field functions
- ODBC [C++], dialog data exchange (DDX) support
- DDX (dialog data exchange) [C++], database support
- DDX (dialog data exchange) [C++], functions
- databases [C++], dialog data exchange (DDX) support
- DAO [C++], dialog data exchange (DDX) support
ms.assetid: 0d8cde38-3a2c-4100-9589-ac80a7b1ce91
caps.latest.revision: 13
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
ms.openlocfilehash: 682c845aa2c915be69aee0d5e95f820573cd6084
ms.lasthandoff: 02/24/2017

---
# <a name="dialog-data-exchange-functions-for-crecordview-and-cdaorecordview"></a>Функции обмена данными в диалоговых окнах для CRecordView и CDaoRecordView
В этом разделе перечислены DDX_Field-функции, используемые для обмена данными между [CRecordset](../../mfc/reference/crecordset-class.md) и [CRecordView](../../mfc/reference/crecordview-class.md) формы или [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md) и [CDaoRecordView](../../mfc/reference/cdaorecordview-class.md) формы.  
  
> [!NOTE]
>  DDX_Field-функции похожи на функции DDX в том, что они обмениваются данными с элементами управления в форме. Но в отличие от DDX, обмена данными с полями представления ассоциированным объектом набора записей, а не с полями записи представления. Дополнительные сведения см. в разделе классы `CRecordView` и `CDaoRecordView`.  
  
### <a name="ddxfield-functions"></a>DDX_Field-функции  
  
|||  
|-|-|  
|[DDX_FieldCBIndex](#ddx_fieldcbindex)|Передает данные целое число между элементом поля данных набора записей и индекс текущего выделенного фрагмента в поле со списком в [CRecordView](../../mfc/reference/crecordview-class.md) или [CDaoRecordView](../../mfc/reference/cdaorecordview-class.md).|  
|[DDX_FieldCBString](#ddx_fieldcbstring)|Передача `CString` поле данных между элементом поля данных набора записей и редактируемый элемент управления поля со списком `CRecordView` или `CDaoRecordView`. При перемещении данных из набора записей в элементе управления, эта функция выбирает элемент в поле со списком, который начинается с символов в указанной строке.|  
|[DDX_FieldCBStringExact](#ddx_fieldcbstringexact)|Передача `CString` поле данных между элементом поля данных набора записей и редактируемый элемент управления поля со списком `CRecordView` или `CDaoRecordView`. При перемещении данных из набора записей в элементе управления, эта функция выбирает элемент в поле со списком, полностью совпадающий с указанной строкой.|  
|[DDX_FieldCheck](#ddx_fieldcheck)|Логическое данные передаются между элементом поля данных набора записей и флажок в `CRecordView` или `CDaoRecordView`.|  
|[DDX_FieldLBIndex](#ddx_fieldlbindex)|Передает данные целое число между элементом поля данных набора записей и индекс текущего выделенного фрагмента в поле со списком в `CRecordView` или `CDaoRecordView`.|  
|[DDX_FieldLBString](#ddx_fieldlbstring)|Управляет передачей [CString](../../atl-mfc-shared/reference/cstringt-class.md) данных между элементом управления списка и элементами данных полей набора записей. При перемещении данных из набора записей в элементе управления, эта функция выбирает элемент в списке, которая начинается с символов в указанной строке.|  
|[DDX_FieldLBStringExact](#ddx_fieldlbstringexact)|Управляет передачей `CString` данных между элементом управления списка и элементами данных полей набора записей. При перемещении данных из набора записей в элементе управления, эта функция выбирает первый элемент, полностью совпадающий с указанной строкой.|  
|[DDX_FieldRadio](#ddx_fieldradio)|Передает данные целое число между элементом поля данных набора записей и группу переключателей в `CRecordView` или `CDaoRecordView`.|  
|[DDX_FieldScroll](#ddx_fieldscroll)|Задает или возвращает позицию прокрутки полосы прокрутки в `CRecordView` или `CDaoRecordView`. Вызов из вашего [DoFieldExchange](../../mfc/reference/cdaorecordset-class.md#dofieldexchange) функции.|  
|[DDX_FieldText](#ddx_fieldtext)|Перегруженные версии будут доступны для передачи `int`, **UINT**, **длинные**, `DWORD`, [CString](../../atl-mfc-shared/reference/cstringt-class.md), **float**, **двойные**, **короткие**, [COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md), и [COleCurrency](../../mfc/reference/colecurrency-class.md) поле данных между элементом поля данных набора записей и изменения `CRecordView` или `CDaoRecordView`.|  
  
##  <a name="ddx_fieldcbindex"></a>DDX_FieldCBIndex  
 `DDX_FieldCBIndex` Функция синхронизирует индекс выбранного элемента в окно списка элемента управления полем со списком в представление записей и `int` членам данных полей в наборе записей, связанный с представлением записи.  
  
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
 Ссылка на член поля данных в связанном `CRecordset` или `CDaoRecordset` объекта.  
  
 `pRecordset`  
 Указатель на [CRecordset](../../mfc/reference/crecordset-class.md) или [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md) объекта при обмене данными.  
  
### <a name="remarks"></a>Примечания  
 При перемещении данных из набора записей в элементе управления, эта функция устанавливает выделение в элементе управления, в зависимости от значения, указанного в *индекса*. При перемещении элемента управления из набора записей Если поля набора записей равен Null, MFC задает значение индекса 0. При перемещении элемента управления в набор записей Если элемент пуст или если элемент не выбран, поля набора записей равен 0.  
  
 Первая версия следует используйте при работе с классами на основе ODBC. Используйте вторую версию при работе с классами на основе DAO.  
  
 Дополнительные сведения об DDX см. в разделе [обмен данными диалоговых окон и проверка](../../mfc/dialog-data-exchange-and-validation.md). Примеры и Дополнительные сведения об ОБМЕНЕ для [CRecordView](../../mfc/reference/crecordview-class.md) и [CDaoRecordView](../../mfc/reference/cdaorecordview-class.md) поля, см. в статье [представления записей](../../data/record-views-mfc-data-access.md).  
  
### <a name="example"></a>Пример  
 В разделе [DDX_FieldText](#ddx_fieldtext) общие DDX_Field пример. Пример будет выглядеть для `DDX_FieldCBIndex`.  

### <a name="requirements"></a>Требования  
 **Заголовок:** afxdao.h  

##  <a name="ddx_fieldcbstring"></a>DDX_FieldCBString  
 `DDX_FieldCBString` Функция управляет передачей [CString](../../atl-mfc-shared/reference/cstringt-class.md) данные между редактируемый элемент управления поля со списком в представление записей и `CString` членам данных полей в наборе записей, связанный с представлением записи.  
  
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
  
 *value*  
 Ссылка на член поля данных в связанном `CRecordset` или `CDaoRecordset` объекта.  
  
 `pRecordset`  
 Указатель на [CRecordset](../../mfc/reference/crecordset-class.md) или [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md) объекта при обмене данными.  
  
### <a name="remarks"></a>Примечания  
 При перемещении данных из набора записей в элементе управления, эта функция задает текущее выделение в поле со списком на первую строку, которая начинается с символов в строку, указанную в *значение*. При перемещении из набора записей в элемент управления, если поле записей имеет значение Null, удаляются все параметры, выбранные из поле со списком и редактируемый элемент управления поля со списком устанавливается на пустой. При перемещении элемента управления в набор записей Если элемент управления является пустым, поля набора записей имеет значение Null Если поле допускает.  
  
 Первая версия следует используйте при работе с классами на основе ODBC. Используйте вторую версию при работе с классами на основе DAO.  
  
 Дополнительные сведения об DDX см. в разделе [обмен данными диалоговых окон и проверка](../../mfc/dialog-data-exchange-and-validation.md). Примеры и Дополнительные сведения об ОБМЕНЕ для [CRecordView](../../mfc/reference/crecordview-class.md) и [CDaoRecordView](../../mfc/reference/cdaorecordview-class.md) поля, см. в статье [представления записей](../../data/record-views-mfc-data-access.md).  
  
### <a name="example"></a>Пример  
 В разделе [DDX_FieldText](#ddx_fieldtext) общие DDX_Field пример. Пример включает вызов `DDX_FieldCBString`.  
  
### <a name="requirements"></a>Требования  
  **Заголовок** afxdao.h  
  
## <a name="ddx_fieldcbstringexact"></a>DDX_FieldCBStringExact  
 `DDX_FieldCBStringExact` Функция управляет передачей [CString](../../atl-mfc-shared/reference/cstringt-class.md) данные между редактируемый элемент управления поля со списком в представление записей и `CString` членам данных полей в наборе записей, связанный с представлением записи.  
  
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
  
 *value*  
 Ссылка на член поля данных в связанном `CRecordset` или `CDaoRecordset` объекта.  
  
 `pRecordset`  
 Указатель на [CRecordset](../../mfc/reference/crecordset-class.md) или [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md) объекта при обмене данными.  
  
### <a name="remarks"></a>Примечания  
 При перемещении данных из набора записей в элементе управления, эта функция задает текущее выделение в первой строке, который точно совпадает со строкой, указанной в поле со списком *значение*. При перемещении из набора записей с элементом управления, если поле записей имеет значение NULL, все параметры, выбранные удаляется из поле со списком, и поле ввода поля со списком задается на пустой. При перемещении элемента управления в набор записей Если элемент управления является пустым, поля набора записей имеет значение NULL.  
  
 Первая версия следует используйте при работе с классами на основе ODBC. Используйте вторую версию при работе с классами на основе DAO.  
  
 Дополнительные сведения об DDX см. в разделе [обмен данными диалоговых окон и проверка](../../mfc/dialog-data-exchange-and-validation.md). Примеры и Дополнительные сведения об ОБМЕНЕ для [CRecordView](../../mfc/reference/crecordview-class.md) и [CDaoRecordView](../../mfc/reference/cdaorecordview-class.md) поля, см. в статье [представления записей](../../data/record-views-mfc-data-access.md).  
  
### <a name="example"></a>Пример  
 В разделе [DDX_FieldText](#ddx_fieldtext) общие DDX_Field пример. Вызовы `DDX_FieldCBStringExact` будет выглядеть.  
  
### <a name="requirements"></a>Требования  
  **Заголовок** afxdao.h  
  
##  <a name="ddx_fieldcheck"></a>DDX_FieldCheck  
 `DDX_FieldCheck` Функция управляет передачей `int` данные между управления "флажок" в диалоговом окне, форму, представление или объект элемента управления представления и `int` диалоговое окно, представление формы или объект элемента управления представления элемента данных.  
  
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
 Идентификатор ресурса управления "флажок", связанный со свойством элемента управления.  
  
 *value*  
 Ссылка на переменную-член диалоговое окно, представление формы или объект элемента управления представления обмене данными.  
  
 `pRecordset`  
 Указатель на [CRecordset](../../mfc/reference/crecordset-class.md) или [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md) объекта при обмене данными.  
  
### <a name="remarks"></a>Примечания  
 При `DDX_FieldCheck` вызывается, *значение* присваивается текущее состояние элемента управления флажком или присвоено состояние элемента управления *значение*, в зависимости от направления передачи.  
  
 Дополнительные сведения об DDX см. в разделе [обмен данными диалоговых окон и проверка](../../mfc/dialog-data-exchange-and-validation.md).  
  
### <a name="requirements"></a>Требования  
  **Заголовок** afxdao.h  
  
##  <a name="ddx_fieldlbindex"></a>DDX_FieldLBIndex  
 `DDX_FieldLBIndex` Функция синхронизирует индекс выбранного элемента в элемент управления списком в представление записей и `int` членам данных полей в наборе записей, связанный с представлением записи.  
  
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
 Ссылка на член поля данных в связанном `CRecordset` или `CDaoRecordset` объекта.  
  
 `pRecordset`  
 Указатель на [CRecordset](../../mfc/reference/crecordset-class.md) или [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md) объекта при обмене данными.  
  
### <a name="remarks"></a>Примечания  
 При перемещении данных из набора записей в элементе управления, эта функция устанавливает выделение в элементе управления, в зависимости от значения, указанного в *индекса*. При перемещении элемента управления из набора записей Если поля набора записей равен Null, MFC задает значение индекса 0. При перемещении элемента управления в набор записей Если элемент управления является пустым, поля набора записей имеет значение 0.  
  
 Первая версия следует используйте при работе с классами на основе ODBC. Используйте вторую версию при работе с классами на основе DAO.  
  
 Дополнительные сведения об DDX см. в разделе [обмен данными диалоговых окон и проверка](../../mfc/dialog-data-exchange-and-validation.md). Примеры и Дополнительные сведения об ОБМЕНЕ для [CRecordView](../../mfc/reference/crecordview-class.md) и [CDaoRecordView](../../mfc/reference/cdaorecordview-class.md) поля, см. в статье [представления записей](../../data/record-views-mfc-data-access.md).  
  
### <a name="example"></a>Пример  
 В разделе [DDX_FieldText](#ddx_fieldtext) общие DDX_Field пример.  
  
### <a name="requirements"></a>Требования  
  **Заголовок** afxdao.h  
  
##  <a name="ddx_fieldlbstring"></a>DDX_FieldLBString  
 `DDX_FieldLBString` Копирует текущее выделение окно списка в представлении записей для [CString](../../atl-mfc-shared/reference/cstringt-class.md) членам данных полей в наборе записей, связанный с представлением записи.  
  
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
  
 *value*  
 Ссылка на член поля данных в связанном `CRecordset` или `CDaoRecordset` объекта.  
  
 `pRecordset`  
 Указатель на [CRecordset](../../mfc/reference/crecordset-class.md) или [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md) объекта при обмене данными.  
  
### <a name="remarks"></a>Примечания  
 В обратном направлении, эта функция задает текущее выделение в поле со списком на первую строку, которая начинается с символов в строки, заданной параметром *значение*. При перемещении элемента управления из набора записей Если поля набора записей имеет значение Null, все параметры, выбранные удаляется из списка. При перемещении элемента управления в набор записей Если элемент управления является пустым, поля набора записей имеет значение Null.  
  
 Первая версия следует используйте при работе с классами на основе ODBC. Используйте вторую версию при работе с классами на основе DAO.  
  
 Дополнительные сведения об DDX см. в разделе [обмен данными диалоговых окон и проверка](../../mfc/dialog-data-exchange-and-validation.md). Примеры и Дополнительные сведения об ОБМЕНЕ для [CRecordView](../../mfc/reference/crecordview-class.md) и [CDaoRecordView](../../mfc/reference/cdaorecordview-class.md) поля, см. в статье [представления записей](../../data/record-views-mfc-data-access.md).  
  
### <a name="example"></a>Пример  
 В разделе [DDX_FieldText](#ddx_fieldtext) общие DDX_Field пример. Вызовы `DDX_FieldLBString` будет выглядеть.  
  
### <a name="requirements"></a>Требования  
  **Заголовок** afxdao.h  
  
##  <a name="ddx_fieldlbstringexact"></a>DDX_FieldLBStringExact  
 `DDX_FieldLBStringExact` Функция копирует текущее выделение окно списка в представлении записей для [CString](../../atl-mfc-shared/reference/cstringt-class.md) членам данных полей в наборе записей, связанный с представлением записи.  
  
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
  
 *value*  
 Ссылка на член поля данных в связанном `CRecordset` или `CDaoRecordset` объекта.  
  
 `pRecordset`  
 Указатель на [CRecordset](../../mfc/reference/crecordset-class.md) или [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md) объекта при обмене данными.  
  
### <a name="remarks"></a>Примечания  
 В обратном направлении, эта функция задает текущее выделение в поле со списком на первую строку, которая точно совпадает со строкой, указанной в *значение*. При перемещении элемента управления из набора записей Если поля набора записей имеет значение Null, все параметры, выбранные удаляется из списка. При перемещении элемента управления в набор записей Если элемент управления является пустым, поля набора записей имеет значение Null.  
  
 Первая версия следует используйте при работе с классами на основе ODBC. Используйте вторую версию при работе с классами на основе DAO.  
  
 Дополнительные сведения об DDX см. в разделе [обмен данными диалоговых окон и проверка](../../mfc/dialog-data-exchange-and-validation.md). Примеры и Дополнительные сведения об ОБМЕНЕ для [CRecordView](../../mfc/reference/crecordview-class.md) и [CDaoRecordView](../../mfc/reference/cdaorecordview-class.md) поля, см. в статье [представления записей](../../data/record-views-mfc-data-access.md).  
  
### <a name="example"></a>Пример  
 В разделе [DDX_FieldText](#ddx_fieldtext) общие DDX_Field пример. Вызовы `DDX_FieldLBStringExact` будет выглядеть.  
  
### <a name="requirements"></a>Требования  
  **Заголовок** afxdao.h  
  
##  <a name="ddx_fieldradio"></a>DDX_FieldRadio  
 `DDX_FieldRadio` Функция связывает отсчитываемый от нуля `int` переменной-члена набора записей представления записей с помощью выбранного переключателя в группе переключателей в представлении записей.  
  
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
 Идентификатор первого в группе (стилем **WS_GROUP**) возле переключателей в [CRecordView](../../mfc/reference/crecordview-class.md) или [CDaoRecordView](../../mfc/reference/cdaorecordview-class.md) объекта.  
  
 *value*  
 Ссылка на член поля данных в связанном `CRecordset` или `CDaoRecordset` объекта.  
  
 `pRecordset`  
 Указатель на [CRecordset](../../mfc/reference/crecordset-class.md) или [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md) объекта при обмене данными.  
  
### <a name="remarks"></a>Примечания  
 При переносе из поля набора записей в представлении, эта функция включает *n-й* переключатель (от нуля), а также отключается другие кнопки. В обратном направлении эта функция устанавливает для поля набора записей с порядковым номером переключателя, который включен в данный момент (флажок установлен). При перемещении элемента управления из набора записей Если поля набора записей имеет значение Null, не выбран. При перемещении элемента управления в набор записей Если не выделен поля набора записей имеет значение Null Если поле допускает.  
  
 Первая версия следует используйте при работе с классами на основе ODBC. Используйте вторую версию при работе с классами на основе DAO.  
  
 Дополнительные сведения об DDX см. в разделе [обмен данными диалоговых окон и проверка](../../mfc/dialog-data-exchange-and-validation.md). Примеры и Дополнительные сведения об ОБМЕНЕ для [CRecordView](../../mfc/reference/crecordview-class.md) и [CDaoRecordView](../../mfc/reference/cdaorecordview-class.md) поля, см. в статье [представления записей](../../data/record-views-mfc-data-access.md).  
  
### <a name="example"></a>Пример  
 В разделе [DDX_FieldText](#ddx_fieldtext) общие DDX_Field пример. Вызовы `DDX_FieldRadio` будет выглядеть.  
  
### <a name="requirements"></a>Требования  
  **Заголовок** afxdao.h  
  
##  <a name="ddx_fieldscroll"></a>DDX_FieldScroll  
 `DDX_FieldScroll` Функция синхронизирует позицию прокрутки полосы прокрутки в представлении записей и `int` членам данных полей в наборе записей, связанный с представлением записи (или любой целочисленной переменной, выберите его, чтобы сопоставить).  
  
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
 Идентификатор первого в группе (стилем **WS_GROUP**) возле переключателей в [CRecordView](../../mfc/reference/crecordview-class.md) или [CDaoRecordView](../../mfc/reference/cdaorecordview-class.md) объекта.  
  
 *value*  
 Ссылка на член поля данных в связанном `CRecordset` или `CDaoRecordset` объекта.  
  
 `pRecordset`  
 Указатель на [CRecordset](../../mfc/reference/crecordset-class.md) или [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md) объекта при обмене данными.  
  
### <a name="remarks"></a>Примечания  
 При перемещении данных из набора записей в элементе управления, эта функция задает позицию прокрутки полосы прокрутки для значения, указанного в *значение*. При перемещении элемента управления из набора записей Если поля набора записей равен Null, полосы прокрутки имеет значение 0. При перемещении элемента управления в набор записей Если элемент управления является пустым, значение поля набора записей — 0.  
  
 Первая версия следует используйте при работе с классами на основе ODBC. Используйте вторую версию при работе с классами на основе DAO.  
  
 Дополнительные сведения об DDX см. в разделе [обмен данными диалоговых окон и проверка](../../mfc/dialog-data-exchange-and-validation.md). Примеры и Дополнительные сведения об ОБМЕНЕ для [CRecordView](../../mfc/reference/crecordview-class.md) и [CDaoRecordView](../../mfc/reference/cdaorecordview-class.md) поля, см. в статье [представления записей](../../data/record-views-mfc-data-access.md).  
  
### <a name="example"></a>Пример  
 В разделе [DDX_FieldText](#ddx_fieldtext) общие DDX_Field пример. Вызовы `DDX_FieldScroll` будет выглядеть.  
  
### <a name="requirements"></a>Требования  
  **Заголовок** afxdao.h  
  
##  <a name="ddx_fieldtext"></a>DDX_FieldText  
 `DDX_FieldText` Функция управляет передачей `int`, **короткие**, **длинные**, `DWORD`, [CString](../../atl-mfc-shared/reference/cstringt-class.md), **float**, **двойные**, **BOOL**, или **БАЙТОВ** данных между поля ввода и элементами данных полей набора записей.  
  
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
  
 *value*  
 Ссылка на член поля данных в связанном `CRecordset` или `CDaoRecordset` объекта. Тип данных значения зависит от того, какие из перегруженных версий `DDX_FieldText` использовании.  
  
 `pRecordset`  
 Указатель на [CRecordset](../../mfc/reference/crecordset-class.md) или [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md) объекта при обмене данными. Этот указатель позволяет `DDX_FieldText` для обнаружения и установки значений Null.  
  
### <a name="remarks"></a>Примечания  
 Для [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md) объектов, `DDX_FieldText` также управляет передачи [COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md), и [COleCurrency](../../mfc/reference/colecurrency-class.md) значения. Пустой элемент управления поле указывает значение Null. При перемещении элемента управления из набора записей, если поля набора записей равен Null, задано поле ввода пустым. При перемещении элемента управления в набор записей Если элемент управления является пустым, поля набора записей имеет значение Null.  
  
 Использование версии с [CRecordset](../../mfc/reference/crecordset-class.md) параметры при работе с классами на основе ODBC. Использование версии с [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md) параметры при работе с классами на основе DAO.  
  
 Дополнительные сведения об DDX см. в разделе [обмен данными диалоговых окон и проверка](../../mfc/dialog-data-exchange-and-validation.md). Примеры и Дополнительные сведения об ОБМЕНЕ для [CRecordView](../../mfc/reference/crecordview-class.md) и [CDaoRecordView](../../mfc/reference/cdaorecordview-class.md) поля, см. в статье [представления записей](../../data/record-views-mfc-data-access.md).  
  
### <a name="example"></a>Пример  
 Следующие `DoDataExchange` функции для [CRecordView](../../mfc/reference/crecordview-class.md) содержит `DDX_FieldText` функция вызывает для трех типов данных: `IDC_COURSELIST` является списком; находятся два других элемента управления поля ввода. Для программирования DAO *m_pSet* параметр — указатель на [CRecordset](../../mfc/reference/crecordset-class.md) или [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md).  
  
 [!code-cpp[NVC_MFCDatabase&#43;](../../mfc/codesnippet/cpp/dialog-data-exchange-functions-for-crecordview-and-cdaorecordview_1.cpp)]  

  
### <a name="requirements"></a>Требования  
  **Заголовок** afxdao.h  
    
## <a name="see-also"></a>См. также  
 [Макросы и глобальные объекты](../../mfc/reference/mfc-macros-and-globals.md)

