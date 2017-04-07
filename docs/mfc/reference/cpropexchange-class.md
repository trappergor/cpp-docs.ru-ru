---
title: "Класс CPropExchange | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
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
- CPropExchange class
- OLE controls, persistence
- controls [MFC], OLE
ms.assetid: ed872180-e770-4942-892a-92139d501fab
caps.latest.revision: 22
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
ms.openlocfilehash: 655d8e2f074c3bd12b1b52ece74efb844c7a9904
ms.lasthandoff: 02/24/2017

---
# <a name="cpropexchange-class"></a>Класс CPropExchange
Поддерживает реализацию сохранения элементов управления OLE.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class AFX_NOVTABLE CPropExchange  
```  
  
## <a name="members"></a>Члены  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CPropExchange::ExchangeBlobProp](#exchangeblobprop)|Меняет местами свойство большого двоичного объекта (BLOB).|  
|[CPropExchange::ExchangeFontProp](#exchangefontprop)|Меняет местами свойства шрифта.|  
|[CPropExchange::ExchangePersistentProp](#exchangepersistentprop)|Меняет местами свойства между элементом управления и файл.|  
|[CPropExchange::ExchangeProp](#exchangeprop)|Меняет местами свойства любого встроенного типа.|  
|[CPropExchange::ExchangeVersion](#exchangeversion)|Меняет местами номер версии элемента управления OLE.|  
|[CPropExchange::GetVersion](#getversion)|Извлекает номер версии элемента управления OLE.|  
|[CPropExchange::IsAsynchronous](#isasynchronous)|Определяет свойство обмен выполняются асинхронно.|  
|[CPropExchange::IsLoading](#isloading)|Указывает, выполняется ли свойства загрузки или сохранения из него.|  
  
## <a name="remarks"></a>Примечания  
 `CPropExchange`не имеет базового класса.  
  
 Устанавливает контекст и направление exchange свойство.  
  
 Сохраняемости является обмен информации о состоянии элемента управления, как правило, представляется его свойства, от самого элемента управления и носитель.  
  
 Платформа создает объект, производный от `CPropExchange` при его уведомляется, что свойства элемента управления OLE могут быть загружены из или хранимые процедуры для постоянного хранения.  
  
 Платформа передает указатель на это `CPropExchange` объект для элемента управления `DoPropExchange` функции. При использовании мастера для создания начальных файлов для, элемент управления элемента управления `DoPropExchange` вызовов функции `COleControl::DoPropExchange`. Версия базового класса обменивается стандартных свойств элемента управления; изменить версию производного класса к свойствам exchange, добавленных в элемент управления.  
  
 `CPropExchange`можно использовать для сериализации свойств элемента управления или инициализации свойств элемента управления после загрузки или создания элементов управления. `ExchangeProp` И `ExchangeFontProp` функции-члены `CPropExchange` могут хранить свойства и загрузить их из разных мультимедиа.  
  
 Дополнительные сведения об использовании `CPropExchange`, см. в статье [элементы управления ActiveX в MFC: страницы свойств](../../mfc/mfc-activex-controls-property-pages.md).  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 `CPropExchange`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxctl.h  
  
##  <a name="exchangeblobprop"></a>CPropExchange::ExchangeBlobProp  
 Сериализует свойство, которое хранит данные больших двоичных объектов (BLOB).  
  
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
 Указатель на переменную, указывающую на место хранения свойство (переменная обычно является членом класса).  
  
 `hBlobDefault`  
 Значение по умолчанию для свойства.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если exchange был успешным; 0, если операция завершилась неудачей.  
  
### <a name="remarks"></a>Примечания  
 Значение свойства чтение и запись к, в соответствии с ссылается переменная `phBlob`. Если `hBlobDefault` указан, будет использоваться как значение свойства по умолчанию. Это значение используется в том случае, если по какой-либо причине происходит сбой сериализации элемента управления.  
  
 Функции **CArchivePropExchange::ExchangeBlobProp**, **CResetPropExchange::ExchangeBlobProp**, и **CPropsetPropExchange::ExchangeBlobProp** переопределить это чисто виртуальную функцию.  
  
##  <a name="exchangefontprop"></a>CPropExchange::ExchangeFontProp  
 Меняет местами свойства шрифтов между среду хранения и управления.  
  
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
 Указатель на [FONTDESC](http://msdn.microsoft.com/library/windows/desktop/ms692782) структура, содержащая значения для инициализации состояния по умолчанию свойства шрифта при `pFontDispAmbient` — **NULL**.  
  
 `pFontDispAmbient`  
 Указатель на **IFontDisp** интерфейс шрифта, используемого для инициализации состояния по умолчанию свойства шрифта.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если exchange был успешным; 0, если операция завершилась неудачей.  
  
### <a name="remarks"></a>Примечания  
 Если свойство font загружается с носителя в элемент управления, характеристики шрифта извлекаются с носителя и `CFontHolder` объект ссылается `font` инициализируется с ними. Если хранится свойства шрифта, характеристики шрифта объекта записываются на носитель.  
  
 Функции **CArchivePropExchange::ExchangeFontProp**, **CResetPropExchange::ExchangeFontProp**, и **CPropsetPropExchange::ExchangeFontProp** переопределить это чисто виртуальную функцию.  
  
##  <a name="exchangepersistentprop"></a>CPropExchange::ExchangePersistentProp  
 Меняет местами свойства между элементом управления и файл.  
  
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
 Указатель на переменную, содержащую указатель на значение свойства **IUnknown** интерфейса (эта переменная обычно является членом класса).  
  
 `iid`  
 Идентификатор интерфейса на свойство, которое элемент управления будет использовать интерфейс.  
  
 `pUnkDefault`  
 Значение по умолчанию для свойства.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если exchange был успешным; 0, если операция завершилась неудачей.  
  
### <a name="remarks"></a>Примечания  
 Если свойство загружается из файла к элементу управления, свойство создается и инициализируется из файла. Если это свойство хранится, его значение записывается в файл.  
  
 Функции **CArchivePropExchange::ExchangePersistentProp**, **CResetPropExchange::ExchangePersistentProp**, и **CPropsetPropExchange::ExchangePersistentProp** переопределить это чисто виртуальную функцию.  
  
##  <a name="exchangeprop"></a>CPropExchange::ExchangeProp  
 Меняет местами свойства между среду хранения и управления.  
  
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
|`VT_CY`|**ПОЛУГОДИЕ**|  
|`VT_R4`|**float**|  
|`VT_R8`|**double**|  
  
 `pvProp`  
 Указатель на значение свойства.  
  
 *pvDefault*  
 Указатель на значение по умолчанию для свойства.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если exchange был успешным; 0, если операция завершилась неудачей.  
  
### <a name="remarks"></a>Примечания  
 Если свойство загружается с носителя для элемента управления, значение свойства извлекается с носителя и хранятся в объекте, на который указывает `pvProp`. Если это свойство хранится на носитель, указывает на значение объекта `pvProp` записывается на носитель.  
  
 Функции **CArchivePropExchange::ExchangeProp**, **CResetPropExchange::ExchangeProp**, и **CPropsetPropExchange::ExchangeProp** переопределить это чисто виртуальную функцию.  
  
##  <a name="exchangeversion"></a>CPropExchange::ExchangeVersion  
 Вызывается платформой для обработки сохраняемости номера версии.  
  
```  
virtual BOOL ExchangeVersion(
    DWORD& dwVersionLoaded,  
    DWORD dwVersionDefault,  
    BOOL bConvert);
```  
  
### <a name="parameters"></a>Параметры  
 *dwVersionLoaded*  
 Ссылка на переменную для хранения постоянных загружаемых данных номер версии.  
  
 `dwVersionDefault`  
 Номер текущей версии элемента управления.  
  
 `bConvert`  
 Указывает, следует ли преобразовать постоянных данных в текущей версии или оставить по той же версии, который был загружен.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если функция выполнена успешно; в противном случае — 0.  
  
##  <a name="getversion"></a>CPropExchange::GetVersion  
 Эта функция вызывается для получения номер версии элемента управления.  
  
```  
DWORD GetVersion();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Номер версии элемента управления.  
  
##  <a name="isasynchronous"></a>CPropExchange::IsAsynchronous  
 Определяет свойство обмен выполняются асинхронно.  
  
```  
BOOL IsAsynchronous();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение TRUE, если свойства обмен асинхронно, в противном случае — значение FALSE.  
  
##  <a name="isloading"></a>CPropExchange::IsLoading  
 Эта функция вызывается для определения, выполняется ли свойства загрузки элемента управления или сохранения из него.  
  
```  
BOOL IsLoading();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если свойства загружаются; в противном случае — 0.  
  
## <a name="see-also"></a>См. также  
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [COleControl::DoPropExchange](../../mfc/reference/colecontrol-class.md#dopropexchange)




