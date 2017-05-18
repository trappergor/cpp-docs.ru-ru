---
title: "Класс COleChangeSourceDialog | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
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
- OLE Change Source dialog box
- COleChangeSourceDialog class
- dialog boxes, OLE
- OLE dialog boxes, Change Source
- OleUIChangeSource structure
ms.assetid: d0e08be7-21ef-45e1-97af-fe27d99e3bac
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 040985df34f2613b4e4fae29498721aef15d50cb
ms.openlocfilehash: 4a1af032b9a10a0262f0267056b675eed7da509c
ms.contentlocale: ru-ru
ms.lasthandoff: 02/24/2017

---
# <a name="colechangesourcedialog-class"></a>Класс COleChangeSourceDialog
Используется для диалогового окна OLE "Изменить источник".  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class COleChangeSourceDialog : public COleDialog  
```  
  
## <a name="members"></a>Члены  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[COleChangeSourceDialog::COleChangeSourceDialog](#colechangesourcedialog)|Создает объект `COleChangeSourceDialog`.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[COleChangeSourceDialog::DoModal](#domodal)|Отображение диалогового окна OLE Смена источника.|  
|[COleChangeSourceDialog::GetDisplayName](#getdisplayname)|Получает полный исходный отображаемое имя.|  
|[COleChangeSourceDialog::GetFileName](#getfilename)|Возвращает имя файла из исходного имени.|  
|[COleChangeSourceDialog::GetFromPrefix](#getfromprefix)|Возвращает префикс предыдущего источника.|  
|[COleChangeSourceDialog::GetItemName](#getitemname)|Получает имя от имени источника.|  
|[COleChangeSourceDialog::GetToPrefix](#gettoprefix)|Возвращает префикс нового источника|  
|[COleChangeSourceDialog::IsValidSource](#isvalidsource)|Указывает, является ли допустимым источником.|  
  
### <a name="public-data-members"></a>Открытые члены данных  
  
|Имя|Описание|  
|----------|-----------------|  
|[COleChangeSourceDialog::m_cs](#m_cs)|Структура, которая управляет поведением диалогового окна.|  
  
## <a name="remarks"></a>Примечания  
 Создание объекта класса `COleChangeSourceDialog` при необходимо вызвать это диалоговое окно предназначено. После `COleChangeSourceDialog` объект был создан, можно использовать [m_cs](#m_cs) структуры для инициализации значения или состояния элементов управления в диалоговом окне. `m_cs` Структуры имеет тип [OLEUICHANGESOURCE](http://msdn.microsoft.com/library/windows/desktop/ms682160). Дополнительные сведения об использовании этого класса диалогового окна в разделе [DoModal](#domodal) функции-члена.  
  
 Дополнительные сведения см. в разделе [OLEUICHANGESOURCE](http://msdn.microsoft.com/library/windows/desktop/ms682160) в структуре [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 Дополнительные сведения о диалоговых окнах OLE конкретных см. в статье [диалоговые окна в OLE](../../mfc/dialog-boxes-in-ole.md).  
  
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
  
##  <a name="colechangesourcedialog"></a>COleChangeSourceDialog::COleChangeSourceDialog  
 Эта функция создает `COleChangeSourceDialog` объекта.  
  
```  
explicit COleChangeSourceDialog(
    COleClientItem* pItem,  
    CWnd* pParentWnd = NULL);
```  
  
### <a name="parameters"></a>Параметры  
 `pItem`  
 Указатель на связанный [COleClientItem](../../mfc/reference/coleclientitem-class.md) , источник должен быть обновлен.  
  
 `pParentWnd`  
 Указывает на объект окна родительского или владелец (типа `CWnd`), которому принадлежит объект диалогового окна. Если это **NULL**, родительского окна окно будет присвоено главного окна приложения.  
  
### <a name="remarks"></a>Примечания  
 Чтобы открыть диалоговое окно, вызовите [DoModal](#domodal) функции.  
  
 Дополнительные сведения см. в разделе [OLEUICHANGESOURCE](http://msdn.microsoft.com/library/windows/desktop/ms682160) структуры и [OleUIChangeSource](http://msdn.microsoft.com/library/windows/desktop/ms682497) работать в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="domodal"></a>COleChangeSourceDialog::DoModal  
 Эта функция вызывается для отображения диалогового окна OLE Смена источника.  
  
```  
virtual INT_PTR DoModal();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Состояние завершения для диалогового окна. Одно из следующих значений:  
  
- **IDOK** Если успешно откроется диалоговое окно.  
  
- **IDCANCEL** Если пользователь отменил диалоговое окно.  
  
- **IDABORT** произошла ошибка. Если **IDABORT** будет возвращен, вызовите [COleDialog::GetLastError](../../mfc/reference/coledialog-class.md#getlasterror) функции-члена для получения дополнительных сведений о типе возникшей ошибки. Список возможных ошибок см. в разделе [OleUIChangeSource](http://msdn.microsoft.com/library/windows/desktop/ms682497) работать в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="remarks"></a>Примечания  
 Если требуется инициализировать различные диалоговыми окнами, задав члены [m_cs](#m_cs) структуры, это следует сделать до вызова метода `DoModal`, но после создания объекта диалогового окна.  
  
 Если `DoModal` возвращает **IDOK**, можно вызвать член функции для получения параметров, вводимых пользователем или сведений из диалогового окна. Следующий список имен функций типичный запрос:  
  
- [GetFileName](#getfilename)  
  
- [GetDisplayName](#getdisplayname)  
  
- [GetItemName](#getitemname)  
  
##  <a name="getdisplayname"></a>COleChangeSourceDialog::GetDisplayName  
 Вызовите эту функцию, чтобы получить полное отображаемое имя для элемента связанного клиента.  
  
```  
CString GetDisplayName();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Полный исходный отображаемое имя (moniker) [COleClientItem](../../mfc/reference/coleclientitem-class.md) указанный в конструкторе.  
  
##  <a name="getfilename"></a>COleChangeSourceDialog::GetFileName  
 Эта функция вызывается для получения части моникера файла отображаемое имя для элемента связанного клиента.  
  
```  
CString GetFileName();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Части специального имени файла источника отображаемое имя для [COleClientItem](../../mfc/reference/coleclientitem-class.md) указанный в конструкторе.  
  
### <a name="remarks"></a>Примечания  
 Моникер файла вместе с моникера элемента дает полное отображаемое имя.  
  
##  <a name="getfromprefix"></a>COleChangeSourceDialog::GetFromPrefix  
 Эта функция вызывается для получения предыдущую строку префикса для источника.  
  
```  
CString GetFromPrefix();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Строка префикса предыдущего источника.  
  
### <a name="remarks"></a>Примечания  
 Эта функция только после вызова [DoModal](#domodal) возвращает **IDOK**.  
  
 Это значение получается непосредственно из **lpszFrom** членом [OLEUICHANGESOURCE](http://msdn.microsoft.com/library/windows/desktop/ms682160) структуры.  
  
 Дополнительные сведения см. в разделе [OLEUICHANGESOURCE](http://msdn.microsoft.com/library/windows/desktop/ms682160) в структуре [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="getitemname"></a>COleChangeSourceDialog::GetItemName  
 Эта функция вызывается для получения части моникер элемента отображаемое имя для элемента связанного клиента.  
  
```  
CString GetItemName();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Моникер элемента часть источника отображаемое имя для [COleClientItem](../../mfc/reference/coleclientitem-class.md) указанный в конструкторе.  
  
### <a name="remarks"></a>Примечания  
 Моникер файла вместе с моникера элемента дает полное отображаемое имя.  
  
##  <a name="gettoprefix"></a>COleChangeSourceDialog::GetToPrefix  
 Эта функция вызывается для получения новых строка префикса для источника.  
  
```  
CString GetToPrefix();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Новая строка префикса источника.  
  
### <a name="remarks"></a>Примечания  
 Эта функция только после вызова [DoModal](#domodal) возвращает **IDOK**.  
  
 Это значение получается непосредственно из **lpszTo** членом [OLEUICHANGESOURCE](http://msdn.microsoft.com/library/windows/desktop/ms682160) структуры.  
  
 Дополнительные сведения см. в разделе [OLEUICHANGESOURCE](http://msdn.microsoft.com/library/windows/desktop/ms682160) в структуре [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="m_cs"></a>COleChangeSourceDialog::m_cs  
 Этот член данных представляет структуру типа [OLEUICHANGESOURCE](http://msdn.microsoft.com/library/windows/desktop/ms682160).  
  
```  
OLEUICHANGESOURCE m_cs;  
```  
  
### <a name="remarks"></a>Примечания  
 `OLEUICHANGESOURCE`используется для управления поведением диалогового окна OLE Смена источника. Члены этой структуры можно изменять непосредственно.  
  
 Дополнительные сведения см. в разделе [OLEUICHANGESOURCE](http://msdn.microsoft.com/library/windows/desktop/ms682160) в структуре [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="isvalidsource"></a>COleChangeSourceDialog::IsValidSource  
 Эта функция используется для определения того, допустим ли новый источник.  
  
```  
BOOL IsValidSource();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если новый источник является допустимым, в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Эта функция только после вызова [DoModal](#domodal) возвращает **IDOK**.  
  
 Дополнительные сведения см. в разделе [OLEUICHANGESOURCE](http://msdn.microsoft.com/library/windows/desktop/ms682160) в структуре [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
## <a name="see-also"></a>См. также  
 [Класс COleDialog](../../mfc/reference/coledialog-class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Класс COleDialog](../../mfc/reference/coledialog-class.md)

