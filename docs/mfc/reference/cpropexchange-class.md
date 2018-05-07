---
title: Класс CPropExchange | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CPropExchange
- AFXCTL/CPropExchange
- AFXCTL/CPropExchange::ExchangeBlobProp
- AFXCTL/CPropExchange::ExchangeFontProp
- AFXCTL/CPropExchange::ExchangePersistentProp
- AFXCTL/CPropExchange::ExchangeProp
- AFXCTL/CPropExchange::ExchangeVersion
- AFXCTL/CPropExchange::GetVersion
- AFXCTL/CPropExchange::IsAsynchronous
- AFXCTL/CPropExchange::IsLoading
dev_langs:
- C++
helpviewer_keywords:
- CPropExchange [MFC], ExchangeBlobProp
- CPropExchange [MFC], ExchangeFontProp
- CPropExchange [MFC], ExchangePersistentProp
- CPropExchange [MFC], ExchangeProp
- CPropExchange [MFC], ExchangeVersion
- CPropExchange [MFC], GetVersion
- CPropExchange [MFC], IsAsynchronous
- CPropExchange [MFC], IsLoading
ms.assetid: ed872180-e770-4942-892a-92139d501fab
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 5f234b3f06e22308a31e8e5694648fd5664b448a
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="cpropexchange-class"></a>Класс CPropExchange
Поддерживает реализацию сохранения элементов управления OLE.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class AFX_NOVTABLE CPropExchange  
```  
  
## <a name="members"></a>Участники  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CPropExchange::ExchangeBlobProp](#exchangeblobprop)|Меняет свойства больших двоичных объектов (BLOB).|  
|[CPropExchange::ExchangeFontProp](#exchangefontprop)|Меняет свойства шрифта.|  
|[CPropExchange::ExchangePersistentProp](#exchangepersistentprop)|Меняет свойства между элементом управления и файл.|  
|[CPropExchange::ExchangeProp](#exchangeprop)|Меняет свойства любого встроенного типа.|  
|[CPropExchange::ExchangeVersion](#exchangeversion)|Меняет местами номер версии элемента управления OLE.|  
|[CPropExchange::GetVersion](#getversion)|Возвращает номер версии элемента управления OLE.|  
|[CPropExchange::IsAsynchronous](#isasynchronous)|Определяет свойство обмен выполняются асинхронно.|  
|[CPropExchange::IsLoading](#isloading)|Указывает, выполняется ли свойства загрузки в элемент управления или сохранения из него.|  
  
## <a name="remarks"></a>Примечания  
 `CPropExchange` не имеет базового класса.  
  
 Устанавливает контекст и направление exchange свойство.  
  
 Сохранение — обмен информации о состоянии элемента управления, как правило, представляется его свойства, от самого элемента управления и среднего.  
  
 Платформа создает объект, производный от `CPropExchange` когда он получит уведомление о том, должны быть загружены из свойства элемента управления OLE или хранимые процедуры для постоянного хранения.  
  
 Это платформа передает указатель `CPropExchange` объект для элемента управления `DoPropExchange` функции. При использовании мастера для создания начальный набор файлов для элемент управления, элемент управления имеет `DoPropExchange` вызовов функций `COleControl::DoPropExchange`. Версия базового класса меняет стандартных свойств элемента управления; Измените версию производного класса к свойствам exchange были добавлены в элемент управления.  
  
 `CPropExchange` можно использовать для сериализации свойства элемента управления или инициализировать свойства элемента управления, после загрузки или создания элементов управления. `ExchangeProp` И `ExchangeFontProp` функции-члены `CPropExchange` могут свойства, чтобы сохранить и загрузить их с другой носитель.  
  
 Дополнительные сведения об использовании `CPropExchange`, см. в статье [элементы управления MFC ActiveX: страницы свойств](../../mfc/mfc-activex-controls-property-pages.md).  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 `CPropExchange`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxctl.h  
  
##  <a name="exchangeblobprop"></a>  CPropExchange::ExchangeBlobProp  
 Сериализует свойство, которое сохраняет данные больших двоичных объектов (BLOB).  
  
```  
virtual BOOL ExchangeBlobProp(
    LPCTSTR pszPropName,  
    HGLOBAL* phBlob,  
    HGLOBAL hBlobDefault = NULL) = 0;  
```  
  
### <a name="parameters"></a>Параметры  
 `pszPropName`  
 Имя свойства при обмене.  
  
 `phBlob`  
 Указатель на переменную, указывающую на место хранения свойство (переменная обычно является элементом класса).  
  
 `hBlobDefault`  
 Значение по умолчанию для свойства.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если exchange был успешным; 0, если операция завершилась неудачей.  
  
### <a name="remarks"></a>Примечания  
 Значение этого свойства чтение и запись к соответствующим образом ссылается переменная `phBlob`. Если `hBlobDefault` указано, оно будет использоваться как значение свойства по умолчанию. Это значение используется в том случае, если по какой-либо причине происходит сбой сериализации элемента управления.  
  
 Функции **CArchivePropExchange::ExchangeBlobProp**, **CResetPropExchange::ExchangeBlobProp**, и **CPropsetPropExchange::ExchangeBlobProp** переопределения Это чистой виртуальной функции.  
  
##  <a name="exchangefontprop"></a>  CPropExchange::ExchangeFontProp  
 Меняет свойства шрифта между носителя и элементом управления.  
  
```  
virtual BOOL ExchangeFontProp(
    LPCTSTR pszPropName,  
    CFontHolder& font,  
    const FONTDESC* pFontDesc,  
    LPFONTDISP pFontDispAmbient) = 0;  
```  
  
### <a name="parameters"></a>Параметры  
 `pszPropName`  
 Имя свойства при обмене.  
  
 `font`  
 Ссылку на [CFontHolder](../../mfc/reference/cfontholder-class.md) , содержащий свойства шрифта.  
  
 `pFontDesc`  
 Указатель на [FONTDESC](http://msdn.microsoft.com/library/windows/desktop/ms692782) структуру, содержащую значения для инициализации состояния свойства шрифта по умолчанию при `pFontDispAmbient` — **NULL**.  
  
 `pFontDispAmbient`  
 Указатель на **IFontDisp** интерфейс шрифта, используемого для инициализации состояния свойства шрифта по умолчанию.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если exchange был успешным; 0, если операция завершилась неудачей.  
  
### <a name="remarks"></a>Примечания  
 Если свойство font загружается с носителя в элемент управления, характеристики шрифта, извлекаются с носителя и `CFontHolder` объект, упоминаемый в `font` инициализируется с ними. Если свойство font хранится, характеристики шрифта объекта записываются на носитель.  
  
 Функции **CArchivePropExchange::ExchangeFontProp**, **CResetPropExchange::ExchangeFontProp**, и **CPropsetPropExchange::ExchangeFontProp** переопределения Это чистой виртуальной функции.  
  
##  <a name="exchangepersistentprop"></a>  CPropExchange::ExchangePersistentProp  
 Меняет свойства между элементом управления и файл.  
  
```  
virtual BOOL ExchangePersistentProp(
    LPCTSTR pszPropName,  
    LPUNKNOWN* ppUnk,  
    REFIID iid,  
    LPUNKNOWN pUnkDefault) = 0;  
```  
  
### <a name="parameters"></a>Параметры  
 `pszPropName`  
 Имя свойства при обмене.  
  
 `ppUnk`  
 Указатель на переменную, содержащую указатель на значение свойства **IUnknown** интерфейса (эта переменная обычно является элементом класса).  
  
 `iid`  
 Идентификатор интерфейса интерфейса в свойство, которое будет использовать элемент управления.  
  
 `pUnkDefault`  
 Значение по умолчанию для свойства.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если exchange был успешным; 0, если операция завершилась неудачей.  
  
### <a name="remarks"></a>Примечания  
 Если свойство загружается из файла в элемент управления, свойство создается и инициализируется из файла. Если это свойство хранится, его значение будет записан в файл.  
  
 Функции **CArchivePropExchange::ExchangePersistentProp**, **CResetPropExchange::ExchangePersistentProp**, и **CPropsetPropExchange::ExchangePersistentProp** переопределить это чистой виртуальной функции.  
  
##  <a name="exchangeprop"></a>  CPropExchange::ExchangeProp  
 Меняет свойства между носителя и элементом управления.  
  
```  
virtual BOOL ExchangeProp(
    LPCTSTR pszPropName,  
    VARTYPE vtProp,  
    void* pvProp,  
    const void* pvDefault = NULL) = 0 ;  
```  
  
### <a name="parameters"></a>Параметры  
 `pszPropName`  
 Имя свойства при обмене.  
  
 `vtProp`  
 Символ, указывающий тип свойства при обмене. Доступны следующие значения:  
  
|Символ|Тип свойства|  
|------------|-------------------|  
|`VT_I2`|**short**|  
|`VT_I4`|**long**|  
|`VT_BOOL`|**BOOL**|  
|`VT_BSTR`|`CString`|  
|`VT_CY`|**CY**|  
|`VT_R4`|**float**|  
|`VT_R8`|**double**|  
  
 `pvProp`  
 Указатель на значение свойства.  
  
 *pvDefault*  
 Указатель на значение по умолчанию для свойства.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если exchange был успешным; 0, если операция завершилась неудачей.  
  
### <a name="remarks"></a>Примечания  
 Если свойство загружается с носителя в элемент управления, значение свойства извлекается с носителя и хранятся в объекте, на который указывает `pvProp`. Если это свойство хранится для среды, значение объекта ссылается `pvProp` записывается на носитель.  
  
 Функции **CArchivePropExchange::ExchangeProp**, **CResetPropExchange::ExchangeProp**, и **CPropsetPropExchange::ExchangeProp** этом чисто переопределения виртуальная функция.  
  
##  <a name="exchangeversion"></a>  CPropExchange::ExchangeVersion  
 Вызывается платформой для обработки сохраняемости номера версии.  
  
```  
virtual BOOL ExchangeVersion(
    DWORD& dwVersionLoaded,  
    DWORD dwVersionDefault,  
    BOOL bConvert);
```  
  
### <a name="parameters"></a>Параметры  
 *dwVersionLoaded*  
 Ссылка на переменную, в которой будет храниться номер версии постоянные данные, загружаемые.  
  
 `dwVersionDefault`  
 Текущий номер версии элемента управления.  
  
 `bConvert`  
 Указывает, следует ли преобразовать постоянных данных до текущей версии или сохранить его в той же версии, который был загружен.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если функция выполнена успешно; в противном случае — 0.  
  
##  <a name="getversion"></a>  CPropExchange::GetVersion  
 Вызывайте эту функцию, чтобы получить номер версии элемента управления.  
  
```  
DWORD GetVersion();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Номер версии элемента управления.  
  
##  <a name="isasynchronous"></a>  CPropExchange::IsAsynchronous  
 Определяет свойство обмен выполняются асинхронно.  
  
```  
BOOL IsAsynchronous();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение TRUE, если свойства обмен асинхронно, в противном случае — значение FALSE.  
  
##  <a name="isloading"></a>  CPropExchange::IsLoading  
 Эта функция вызывается для определения, выполняется ли свойства загрузки в элемент управления или сохранения из него.  
  
```  
BOOL IsLoading();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если свойства загружаются; в противном случае — 0.  
  
## <a name="see-also"></a>См. также  
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [COleControl::DoPropExchange](../../mfc/reference/colecontrol-class.md#dopropexchange)



