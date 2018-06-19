---
title: Класс COleConvertDialog | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- COleConvertDialog
- AFXODLGS/COleConvertDialog
- AFXODLGS/COleConvertDialog::COleConvertDialog
- AFXODLGS/COleConvertDialog::DoConvert
- AFXODLGS/COleConvertDialog::DoModal
- AFXODLGS/COleConvertDialog::GetClassID
- AFXODLGS/COleConvertDialog::GetDrawAspect
- AFXODLGS/COleConvertDialog::GetIconicMetafile
- AFXODLGS/COleConvertDialog::GetSelectionType
- AFXODLGS/COleConvertDialog::m_cv
dev_langs:
- C++
helpviewer_keywords:
- COleConvertDialog [MFC], COleConvertDialog
- COleConvertDialog [MFC], DoConvert
- COleConvertDialog [MFC], DoModal
- COleConvertDialog [MFC], GetClassID
- COleConvertDialog [MFC], GetDrawAspect
- COleConvertDialog [MFC], GetIconicMetafile
- COleConvertDialog [MFC], GetSelectionType
- COleConvertDialog [MFC], m_cv
ms.assetid: a7c57714-31e8-4b78-834d-8ddd1b856a1c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 90453d4e8550038493545b691c978b59bda90fad
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33370293"
---
# <a name="coleconvertdialog-class"></a>Класс COleConvertDialog
Дополнительные сведения см. в разделе [OLEUICONVERT](http://msdn.microsoft.com/library/windows/desktop/ms686657) структуры в Windows SDK.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class COleConvertDialog : public COleDialog  
```  
  
## <a name="members"></a>Участники  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[COleConvertDialog::COleConvertDialog](#coleconvertdialog)|Создает объект `COleConvertDialog`.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[COleConvertDialog::DoConvert](#doconvert)|Выполняет преобразование, указанные в диалоговом окне.|  
|[COleConvertDialog::DoModal](#domodal)|Отображение диалогового окна OLE изменение элемента.|  
|[COleConvertDialog::GetClassID](#getclassid)|Возвращает **CLSID** связанные с выбранным элементом.|  
|[COleConvertDialog::GetDrawAspect](#getdrawaspect)|Указывает необходимость рисования элемента в виде значка.|  
|[COleConvertDialog::GetIconicMetafile](#geticonicmetafile)|Возвращает дескриптор метафайла, связанных с формой, преобразованного в значок этого элемента.|  
|[COleConvertDialog::GetSelectionType](#getselectiontype)|Возвращает тип выбранного фрагмента.|  
  
### <a name="public-data-members"></a>Открытые члены данных  
  
|Имя|Описание|  
|----------|-----------------|  
|[COleConvertDialog::m_cv](#m_cv)|Структура, которая управляет поведением окна.|  
  
## <a name="remarks"></a>Примечания  
  
> [!NOTE]
>  Контейнер, созданный мастером код приложения использует этот класс.  
  
 Дополнительные сведения о конкретных OLE диалоговым окнам см. в статье [диалоговые окна в OLE](../../mfc/dialog-boxes-in-ole.md).  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CDialog](../../mfc/reference/cdialog-class.md)  
  
 [CCommonDialog](../../mfc/reference/ccommondialog-class.md)  
  
 [COleDialog](../../mfc/reference/coledialog-class.md)  
  
 `COleConvertDialog`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxodlgs.h  
  
##  <a name="coleconvertdialog"></a>  COleConvertDialog::COleConvertDialog  
 Создает только `COleConvertDialog` объекта.  
  
```  
explicit COleConvertDialog (
    COleClientItem* pItem,
    DWORD dwFlags = CF_SELECTCONVERTTO,
    CLSID* pClassID = NULL,
    CWnd* pParentWnd = NULL);
```  
  
### <a name="parameters"></a>Параметры  
 `pItem`  
 Указывает элемент, чтобы активировать или преобразовать.  
  
 `dwFlags`  
 Создание флаг, который содержит произвольное количество следующие значения, объединенные с помощью битовой операции- или оператор:  
  
- **CF_SELECTCONVERTTO** указывает, что переключатель преобразовать в выберет изначально при вызове диалогового. Это значение по умолчанию.  
  
- **CF_SELECTACTIVATEAS** указывает, что переключатель активировать будут выбираться изначально при вызове диалоговое окно.  
  
- **CF_SETCONVERTDEFAULT** указывает, что класс которого **CLSID** определяется **clsidConvertDefault** членом `m_cv` структуры будет использоваться как значение по умолчанию в списке классов при преобразовать в кнопку-переключатель установлен.  
  
- **CF_SETACTIVATEDEFAULT** указывает, что класс которого **CLSID** определяется **clsidActivateDefault** членом `m_cv` структуры будет использоваться как значение по умолчанию Выбор в списке класс при активации как переключателя.  
  
- **CF_SHOWHELPBUTTON** задает отображение кнопки справки при вызове диалоговым окном.  
  
 `pClassID`  
 Указывает идентификатор CLSID элемента необходимо активировать или преобразованы. Если **NULL**, **CLSID** связанных с `pItem` будет использоваться.  
  
 `pParentWnd`  
 Указывает на объект window родительского или владелец (типа `CWnd`), которому принадлежит объект диалогового окна. Если это **NULL**, главное окно приложения имеет значение родительского диалогового окна.  
  
### <a name="remarks"></a>Примечания  
 Чтобы открыть диалоговое окно, вызовите [DoModal](#domodal) функции.  
  
 Дополнительные сведения см. в разделе [раздел CLSID](http://msdn.microsoft.com/library/windows/desktop/ms691424) и [OLEUICONVERT](http://msdn.microsoft.com/library/windows/desktop/ms686657) структуры.  
  
##  <a name="doconvert"></a>  COleConvertDialog::DoConvert  
 Эта функция вызывается после успешного возвращения из [DoModal](#domodal)из, чтобы преобразовать или активировать объект типа [COleClientItem](../../mfc/reference/coleclientitem-class.md).  
  
```  
BOOL DoConvert(COleClientItem* pItem);
```  
  
### <a name="parameters"></a>Параметры  
 `pItem`  
 Указывает элемент, чтобы активировать или преобразовать. Не может быть **NULL**.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имеет ненулевое значение в случае успешного выполнения, иначе — 0.  
  
### <a name="remarks"></a>Примечания  
 Активировать согласно сведения, выбранный пользователем в диалоговом окне Convert или преобразовать элемент.  
  
##  <a name="domodal"></a>  COleConvertDialog::DoModal  
 Эта функция вызывается для отображения диалогового окна преобразования OLE.  
  
```  
virtual INT_PTR DoModal();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Состояние завершения для диалогового окна. Одно из следующих значений:  
  
- **IDOK** Если успешно откроется диалоговое окно.  
  
- **IDCANCEL** Если пользователь отменил это диалоговое окно.  
  
- **IDABORT** Если произошла ошибка. Если **IDABORT** будет возвращен, вызовите [COleDialog::GetLastError](../../mfc/reference/coledialog-class.md#getlasterror) функции-члена для получения дополнительных сведений о типе возникшей ошибки. Для получения списка возможных ошибок [OleUIConvert](http://msdn.microsoft.com/library/windows/desktop/ms680694) функции в Windows SDK.  
  
### <a name="remarks"></a>Примечания  
 Если требуется инициализировать различные элементы управления диалоговых окон, задав члены [m_cv](#m_cv) структуры, это следует сделать до вызова метода `DoModal`, но после создания объекта диалогового окна.  
  
 Если `DoModal` возвращает **IDOK**, можно вызывать другой член функции для получения параметров или сведения, введенных пользователем в диалоговом окне.  
  
##  <a name="getclassid"></a>  COleConvertDialog::GetClassID  
 Эта функция вызывается для получения **CLSID** связанный с элементом, выбранный в диалоговом окне Convert пользователем.  
  
```  
REFCLSID GetClassID() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 **CLSID** связанный с элементом, который был выбран в диалоговом окне Convert.  
  
### <a name="remarks"></a>Примечания  
 Эта функция только после вызова [DoModal](#domodal) возвращает **IDOK**.  
  
 Дополнительные сведения см. в разделе [раздел CLSID](http://msdn.microsoft.com/library/windows/desktop/ms691424) в Windows SDK.  
  
##  <a name="getdrawaspect"></a>  COleConvertDialog::GetDrawAspect  
 Эта функция вызывается для определения ли пользователь выбрал отображения выбранного элемента в виде значка.  
  
```  
DVASPECT GetDrawAspect() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Метод требуется для отображения объекта.  
  
- `DVASPECT_CONTENT` Возвращается, если не был установлен флажок виде значка.  
  
- `DVASPECT_ICON` Возвращается, если был установлен флажок виде значка.  
  
### <a name="remarks"></a>Примечания  
 Эта функция только после вызова [DoModal](#domodal) возвращает **IDOK**.  
  
 Дополнительные сведения о рисовании аспект см. в разделе [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177) структуру данных в Windows SDK.  
  
##  <a name="geticonicmetafile"></a>  COleConvertDialog::GetIconicMetafile  
 Эта функция вызывается для получения дескриптора метафайла, содержащий аспект, преобразованного в значок выбранного элемента.  
  
```  
HGLOBAL GetIconicMetafile() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Дескриптор метафайла, содержащий преобразованного в значок аспектом выбранного элемента, если был установлен флажок виде значка проверяется при отклонении диалоговое окно, выбрав **ОК**; в противном случае **NULL**.  
  
##  <a name="getselectiontype"></a>  COleConvertDialog::GetSelectionType  
 Эта функция вызывается для определения типа преобразования, выбранного в диалоговом окне Convert.  
  
```  
UINT GetSelectionType() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Тип выбора объектов.  
  
### <a name="remarks"></a>Примечания  
 Тип возвращаемого значения задаются **выбора** тип перечисления, объявленный в `COleConvertDialog` класса.  
  
```  
enum Selection {
    noConversion,
    convertItem,
    activateAs
    };  
```  
  
 Выполните краткое описание каждого из этих значений.  
  
- **COleConvertDialog::noConversion** возвращаются, если диалоговое окно было отменено или пользователь выбрал без преобразования. Если `COleConvertDialog::DoModal` возвращается **IDOK**, возможно, что пользователь выбрал свой значок, отличной от ранее выбранных.  
  
- **COleConvertDialog::convertItem** возвращается, если установлен переключатель преобразования, пользователь выбирает другой элемент для преобразования, и `DoModal` возвращается **IDOK**.  
  
- **COleConvertDialog::activateAs** возвращается, если был установлен переключатель активации, пользователь выбирает другой элемент для активации, и `DoModal` возвращается **IDOK**.  
  
##  <a name="m_cv"></a>  COleConvertDialog::m_cv  
 Структура типа **OLEUICONVERT** используется для управления поведением диалоговое окно "преобразование".  
  
```  
OLEUICONVERT m_cv;  
```  
  
### <a name="remarks"></a>Примечания  
 Члены этой структуры можно изменить напрямую или с помощью функций-членов.  
  
 Дополнительные сведения см. в разделе [OLEUICONVERT](http://msdn.microsoft.com/library/windows/desktop/ms686657) структуры в Windows SDK.  
  
## <a name="see-also"></a>См. также  
 [Класс COleDialog](../../mfc/reference/coledialog-class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Класс COleDialog](../../mfc/reference/coledialog-class.md)
