---
title: Класс COleChangeSourceDialog | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- COleChangeSourceDialog
- AFXODLGS/COleChangeSourceDialog
- AFXODLGS/COleChangeSourceDialog::COleChangeSourceDialog
- AFXODLGS/COleChangeSourceDialog::DoModal
- AFXODLGS/COleChangeSourceDialog::GetDisplayName
- AFXODLGS/COleChangeSourceDialog::GetFileName
- AFXODLGS/COleChangeSourceDialog::GetFromPrefix
- AFXODLGS/COleChangeSourceDialog::GetItemName
- AFXODLGS/COleChangeSourceDialog::GetToPrefix
- AFXODLGS/COleChangeSourceDialog::IsValidSource
- AFXODLGS/COleChangeSourceDialog::m_cs
dev_langs:
- C++
helpviewer_keywords:
- COleChangeSourceDialog [MFC], COleChangeSourceDialog
- COleChangeSourceDialog [MFC], DoModal
- COleChangeSourceDialog [MFC], GetDisplayName
- COleChangeSourceDialog [MFC], GetFileName
- COleChangeSourceDialog [MFC], GetFromPrefix
- COleChangeSourceDialog [MFC], GetItemName
- COleChangeSourceDialog [MFC], GetToPrefix
- COleChangeSourceDialog [MFC], IsValidSource
- COleChangeSourceDialog [MFC], m_cs
ms.assetid: d0e08be7-21ef-45e1-97af-fe27d99e3bac
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: a8b2ca6ebbc0201a3c56c9239b665c55ccd9eb13
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/29/2018
ms.locfileid: "43202749"
---
# <a name="colechangesourcedialog-class"></a>Класс COleChangeSourceDialog
Используется для диалогового окна OLE "Изменить источник".  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class COleChangeSourceDialog : public COleDialog  
```  
  
## <a name="members"></a>Участники  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[COleChangeSourceDialog::COleChangeSourceDialog](#colechangesourcedialog)|Создает объект `COleChangeSourceDialog`.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[COleChangeSourceDialog::DoModal](#domodal)|Отображает диалоговое окно OLE изменение источника.|  
|[COleChangeSourceDialog::GetDisplayName](#getdisplayname)|Получает полный исходный отображаемое имя.|  
|[COleChangeSourceDialog::GetFileName](#getfilename)|Получает имя файла из имя источника.|  
|[COleChangeSourceDialog::GetFromPrefix](#getfromprefix)|Получает префикс предыдущего источника.|  
|[COleChangeSourceDialog::GetItemName](#getitemname)|Получает имя элемента, от имени исходного.|  
|[COleChangeSourceDialog::GetToPrefix](#gettoprefix)|Получает префикс нового источника|  
|[COleChangeSourceDialog::IsValidSource](#isvalidsource)|Указывает, если источник является допустимым.|  
  
### <a name="public-data-members"></a>Открытые члены данных  
  
|Имя|Описание:|  
|----------|-----------------|  
|[COleChangeSourceDialog::m_cs](#m_cs)|Структура, которая управляет поведением окна.|  
  
## <a name="remarks"></a>Примечания  
 Создайте объект класса `COleChangeSourceDialog` при необходимости вызвать это диалоговое окно. После `COleChangeSourceDialog` объект был создан, можно использовать [m_cs](#m_cs) структуры для инициализации значения или состояния элементов управления в диалоговом окне. `m_cs` Структуры имеет тип [OLEUICHANGESOURCE](/windows/desktop/api/oledlg/ns-oledlg-tagoleuichangesourcea). Дополнительные сведения об использовании этого класса диалогового окна см. в разделе [DoModal](#domodal) функция-член.  
  
 Дополнительные сведения см. в разделе [OLEUICHANGESOURCE](/windows/desktop/api/oledlg/ns-oledlg-tagoleuichangesourcea) структуры в пакете Windows SDK.  
  
 Дополнительные сведения о конкретных OLE диалоговым окнам см. в статье [диалоговые окна в OLE](../../mfc/dialog-boxes-in-ole.md).  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CDialog](../../mfc/reference/cdialog-class.md)  
  
 [CCommonDialog](../../mfc/reference/ccommondialog-class.md)  
  
 [COleDialog](../../mfc/reference/coledialog-class.md)  
  
 `COleChangeSourceDialog`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxodlgs.h  
  
##  <a name="colechangesourcedialog"></a>  COleChangeSourceDialog::COleChangeSourceDialog  
 Эта функция создает `COleChangeSourceDialog` объекта.  
  
```  
explicit COleChangeSourceDialog(
    COleClientItem* pItem,  
    CWnd* pParentWnd = NULL);
```  
  
### <a name="parameters"></a>Параметры  
 *pItem*  
 Указатель на связанную [COleClientItem](../../mfc/reference/coleclientitem-class.md) , источник которого должен быть обновлен.  
  
 *pParentWnd*  
 Указывает на объект окна родительский объект или владельца (типа `CWnd`), которому принадлежит объект диалогового окна. Если это значение NULL, родительского окна окно будет присвоено главного окна приложения.  
  
### <a name="remarks"></a>Примечания  
 Чтобы отобразить диалоговое окно, вызовите [DoModal](#domodal) функции.  
  
 Дополнительные сведения см. в разделе [OLEUICHANGESOURCE](/windows/desktop/api/oledlg/ns-oledlg-tagoleuichangesourcea) структуры и [OleUIChangeSource](/windows/desktop/api/oledlg/nf-oledlg-oleuichangesourcea) функции в пакете Windows SDK.  
  
##  <a name="domodal"></a>  COleChangeSourceDialog::DoModal  
 Вызывайте эту функцию для отображения диалогового окна OLE изменение источника.  
  
```  
virtual INT_PTR DoModal();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Состояние завершения для диалогового окна. Одно из следующих значений:  
  
- IDOK, если было успешно отображено диалоговое окно.  
  
- IDCANCEL, если пользователь отменил диалоговое окно.  
  
- IDABORT, если произошла ошибка. Если возвращается IDABORT, вызовите [COleDialog::GetLastError](../../mfc/reference/coledialog-class.md#getlasterror) функция-член для получения дополнительных сведений о типе возникшей ошибки. Список возможных ошибок, см. в разделе [OleUIChangeSource](/windows/desktop/api/oledlg/nf-oledlg-oleuichangesourcea) функции в пакете Windows SDK.  
  
### <a name="remarks"></a>Примечания  
 Если вы хотите инициализировать различных диалоговых путем определения участников [m_cs](#m_cs) структуры, это следует сделать до вызова метода `DoModal`, но после создания объекта диалогового окна.  
  
 Если `DoModal` возвращает IDOK, вы можете вызов функций-членов для получения параметров, вводимых пользователем или сведения в диалоговом окне. Следующий список имен функций типичный запрос:  
  
- [GetFileName](#getfilename)  
  
- [GetDisplayName](#getdisplayname)  
  
- [GetItemName](#getitemname)  
  
##  <a name="getdisplayname"></a>  COleChangeSourceDialog::GetDisplayName  
 Вызывайте эту функцию, чтобы получить полное отображаемое имя для элемента связанного клиента.  
  
```  
CString GetDisplayName();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Полный исходный отображаемое имя (моникер) [COleClientItem](../../mfc/reference/coleclientitem-class.md) указанный в конструкторе.  
  
##  <a name="getfilename"></a>  COleChangeSourceDialog::GetFileName  
 Вызывайте эту функцию для получения часть файлов, моникер отображаемое имя для элемента связанного клиента.  
  
```  
CString GetFileName();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Часть файлов, моникер отображаемое имя источника [COleClientItem](../../mfc/reference/coleclientitem-class.md) указанный в конструкторе.  
  
### <a name="remarks"></a>Примечания  
 Моникер файла вместе с моникер элемента предоставляет полное отображаемое имя.  
  
##  <a name="getfromprefix"></a>  COleChangeSourceDialog::GetFromPrefix  
 Вызовите эту функцию для получения предыдущих строка префикса для источника.  
  
```  
CString GetFromPrefix();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Строка префикса предыдущего источника.  
  
### <a name="remarks"></a>Примечания  
 Эта функция только после вызова [DoModal](#domodal) возвращает IDOK.  
  
 Это значение поступает непосредственно из `lpszFrom` членом [OLEUICHANGESOURCE](/windows/desktop/api/oledlg/ns-oledlg-tagoleuichangesourcea) структуры.  
  
 Дополнительные сведения см. в разделе [OLEUICHANGESOURCE](/windows/desktop/api/oledlg/ns-oledlg-tagoleuichangesourcea) структуры в пакете Windows SDK.  
  
##  <a name="getitemname"></a>  COleChangeSourceDialog::GetItemName  
 Вызывайте эту функцию для получения части моникер элемента отображаемое имя для элемента связанного клиента.  
  
```  
CString GetItemName();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Моникер элемента части источника отображаемое имя для [COleClientItem](../../mfc/reference/coleclientitem-class.md) указанный в конструкторе.  
  
### <a name="remarks"></a>Примечания  
 Моникер файла вместе с моникер элемента предоставляет полное отображаемое имя.  
  
##  <a name="gettoprefix"></a>  COleChangeSourceDialog::GetToPrefix  
 Вызывайте эту функцию для получения новой строки префикса для источника.  
  
```  
CString GetToPrefix();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Новая строка префикса источника.  
  
### <a name="remarks"></a>Примечания  
 Эта функция только после вызова [DoModal](#domodal) возвращает IDOK.  
  
 Это значение поступает непосредственно из `lpszTo` членом [OLEUICHANGESOURCE](/windows/desktop/api/oledlg/ns-oledlg-tagoleuichangesourcea) структуры.  
  
 Дополнительные сведения см. в разделе [OLEUICHANGESOURCE](/windows/desktop/api/oledlg/ns-oledlg-tagoleuichangesourcea) структуры в пакете Windows SDK.  
  
##  <a name="m_cs"></a>  COleChangeSourceDialog::m_cs  
 Этот элемент данных — это структура типа [OLEUICHANGESOURCE](/windows/desktop/api/oledlg/ns-oledlg-tagoleuichangesourcea).  
  
```  
OLEUICHANGESOURCE m_cs;  
```  
  
### <a name="remarks"></a>Примечания  
 `OLEUICHANGESOURCE` используется для управления поведением диалогового окна OLE изменение источника. Члены этой структуры можно изменять непосредственно.  
  
 Дополнительные сведения см. в разделе [OLEUICHANGESOURCE](/windows/desktop/api/oledlg/ns-oledlg-tagoleuichangesourcea) структуры в пакете Windows SDK.  
  
##  <a name="isvalidsource"></a>  COleChangeSourceDialog::IsValidSource  
 Вызывайте эту функцию для определения допустимости нового источника.  
  
```  
BOOL IsValidSource();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если новый источник допустимо; в противном случае 0.  
  
### <a name="remarks"></a>Примечания  
 Эта функция только после вызова [DoModal](#domodal) возвращает IDOK.  
  
 Дополнительные сведения см. в разделе [OLEUICHANGESOURCE](/windows/desktop/api/oledlg/ns-oledlg-tagoleuichangesourcea) структуры в пакете Windows SDK.  
  
## <a name="see-also"></a>См. также  
 [Класс COleDialog](../../mfc/reference/coledialog-class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Класс COleDialog](../../mfc/reference/coledialog-class.md)
