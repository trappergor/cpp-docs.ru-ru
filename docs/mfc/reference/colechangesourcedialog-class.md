---
title: "Класс COleChangeSourceDialog | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
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
dev_langs: C++
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
caps.latest.revision: "22"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: a9eccd25a175479c18a83b5d6ab96753a946e386
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
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
|[COleChangeSourceDialog::DoModal](#domodal)|Отображение диалогового окна OLE изменить источник.|  
|[COleChangeSourceDialog::GetDisplayName](#getdisplayname)|Возвращает отображаемое имя полного исходного.|  
|[COleChangeSourceDialog::GetFileName](#getfilename)|Возвращает имя файла из исходного имени.|  
|[COleChangeSourceDialog::GetFromPrefix](#getfromprefix)|Получает префикс предыдущего источника.|  
|[COleChangeSourceDialog::GetItemName](#getitemname)|Возвращает имя элемента из исходного имени.|  
|[COleChangeSourceDialog::GetToPrefix](#gettoprefix)|Получает префикс нового источника|  
|[COleChangeSourceDialog::IsValidSource](#isvalidsource)|Указывает, является ли допустимым источником.|  
  
### <a name="public-data-members"></a>Открытые члены данных  
  
|Имя|Описание:|  
|----------|-----------------|  
|[COleChangeSourceDialog::m_cs](#m_cs)|Структура, которая управляет поведением окна.|  
  
## <a name="remarks"></a>Примечания  
 Создание объекта класса `COleChangeSourceDialog` при необходимости вызовите данным диалоговым окном. После `COleChangeSourceDialog` объект был создан, можно использовать [m_cs](#m_cs) структуры для инициализации значения или состояния элементов управления в диалоговом окне. `m_cs` Структуры имеет тип [OLEUICHANGESOURCE](http://msdn.microsoft.com/library/windows/desktop/ms682160). Дополнительные сведения об использовании этого класса диалогового окна см. в разделе [DoModal](#domodal) функции-члена.  
  
 Дополнительные сведения см. в разделе [OLEUICHANGESOURCE](http://msdn.microsoft.com/library/windows/desktop/ms682160) Структура пакета SDK для Windows.  
  
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
  
##  <a name="colechangesourcedialog"></a>COleChangeSourceDialog::COleChangeSourceDialog  
 Эта функция создает `COleChangeSourceDialog` объекта.  
  
```  
explicit COleChangeSourceDialog(
    COleClientItem* pItem,  
    CWnd* pParentWnd = NULL);
```  
  
### <a name="parameters"></a>Параметры  
 `pItem`  
 Указатель на связанную [COleClientItem](../../mfc/reference/coleclientitem-class.md) , источник должен быть обновлен.  
  
 `pParentWnd`  
 Указывает на объект window родительского или владелец (типа `CWnd`), которому принадлежит объект диалогового окна. Если это **NULL**, родительское окно диалогового окна будет присвоено главного окна приложения.  
  
### <a name="remarks"></a>Примечания  
 Чтобы открыть диалоговое окно, вызовите [DoModal](#domodal) функции.  
  
 Дополнительные сведения см. в разделе [OLEUICHANGESOURCE](http://msdn.microsoft.com/library/windows/desktop/ms682160) структуры и [OleUIChangeSource](http://msdn.microsoft.com/library/windows/desktop/ms682497) функции в Windows SDK.  
  
##  <a name="domodal"></a>COleChangeSourceDialog::DoModal  
 Эта функция вызывается для отображения диалогового окна OLE изменить источник.  
  
```  
virtual INT_PTR DoModal();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Состояние завершения для диалогового окна. Одно из следующих значений:  
  
- **IDOK** Если успешно откроется диалоговое окно.  
  
- **IDCANCEL** Если пользователь отменил это диалоговое окно.  
  
- **IDABORT** Если произошла ошибка. Если **IDABORT** будет возвращен, вызовите [COleDialog::GetLastError](../../mfc/reference/coledialog-class.md#getlasterror) функции-члена для получения дополнительных сведений о типе возникшей ошибки. Для получения списка возможных ошибок [OleUIChangeSource](http://msdn.microsoft.com/library/windows/desktop/ms682497) функции в Windows SDK.  
  
### <a name="remarks"></a>Примечания  
 Если требуется инициализировать различные элементы управления диалоговых окон, задав члены [m_cs](#m_cs) структуры, это следует сделать до вызова метода `DoModal`, но после создания объекта диалогового окна.  
  
 Если `DoModal` возвращает **IDOK**, можно вызвать член функции извлечения введенных пользователем параметров или сведения из диалогового окна. В следующем списке названы типичный запрос функции:  
  
- [GetFileName](#getfilename)  
  
- [GetDisplayName](#getdisplayname)  
  
- [GetItemName](#getitemname)  
  
##  <a name="getdisplayname"></a>COleChangeSourceDialog::GetDisplayName  
 Эта функция вызывается для получения полное отображаемое имя для элемента связанного клиента.  
  
```  
CString GetDisplayName();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Отображаемое имя полного исходного (специальное имя) для [COleClientItem](../../mfc/reference/coleclientitem-class.md) указанного в конструкторе.  
  
##  <a name="getfilename"></a>COleChangeSourceDialog::GetFileName  
 Эта функция вызывается для получения части файла моникер отображаемое имя для элемента связанного клиента.  
  
```  
CString GetFileName();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Часть отображаемое имя исходного моникера файлов [COleClientItem](../../mfc/reference/coleclientitem-class.md) указанного в конструкторе.  
  
### <a name="remarks"></a>Примечания  
 Моникер файла вместе с моникера элемента дает полное отображаемое имя.  
  
##  <a name="getfromprefix"></a>COleChangeSourceDialog::GetFromPrefix  
 Эта функция вызывается для получения предыдущей строки префикса для источника.  
  
```  
CString GetFromPrefix();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Строка префикса предыдущего источника.  
  
### <a name="remarks"></a>Примечания  
 Эта функция только после вызова [DoModal](#domodal) возвращает **IDOK**.  
  
 Это значение берется непосредственно из **lpszFrom** членом [OLEUICHANGESOURCE](http://msdn.microsoft.com/library/windows/desktop/ms682160) структуры.  
  
 Дополнительные сведения см. в разделе [OLEUICHANGESOURCE](http://msdn.microsoft.com/library/windows/desktop/ms682160) Структура пакета SDK для Windows.  
  
##  <a name="getitemname"></a>COleChangeSourceDialog::GetItemName  
 Эта функция вызывается для получения части моникера элемента отображаемое имя для элемента связанного клиента.  
  
```  
CString GetItemName();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Часть элемента моникер отображаемое имя источника для [COleClientItem](../../mfc/reference/coleclientitem-class.md) указанного в конструкторе.  
  
### <a name="remarks"></a>Примечания  
 Моникер файла вместе с моникера элемента дает полное отображаемое имя.  
  
##  <a name="gettoprefix"></a>COleChangeSourceDialog::GetToPrefix  
 Эта функция вызывается для получения новой строки префикса для источника.  
  
```  
CString GetToPrefix();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Новая строка префикса источника.  
  
### <a name="remarks"></a>Примечания  
 Эта функция только после вызова [DoModal](#domodal) возвращает **IDOK**.  
  
 Это значение берется непосредственно из **lpszTo** членом [OLEUICHANGESOURCE](http://msdn.microsoft.com/library/windows/desktop/ms682160) структуры.  
  
 Дополнительные сведения см. в разделе [OLEUICHANGESOURCE](http://msdn.microsoft.com/library/windows/desktop/ms682160) Структура пакета SDK для Windows.  
  
##  <a name="m_cs"></a>COleChangeSourceDialog::m_cs  
 Этот член данных — структура типа [OLEUICHANGESOURCE](http://msdn.microsoft.com/library/windows/desktop/ms682160).  
  
```  
OLEUICHANGESOURCE m_cs;  
```  
  
### <a name="remarks"></a>Примечания  
 `OLEUICHANGESOURCE`используется для управления поведением диалогового окна OLE изменить источник. Члены этой структуры можно изменять непосредственно.  
  
 Дополнительные сведения см. в разделе [OLEUICHANGESOURCE](http://msdn.microsoft.com/library/windows/desktop/ms682160) Структура пакета SDK для Windows.  
  
##  <a name="isvalidsource"></a>COleChangeSourceDialog::IsValidSource  
 Эта функция вызывается для определения допустимости нового источника.  
  
```  
BOOL IsValidSource();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если новый источник действителен, иначе — 0.  
  
### <a name="remarks"></a>Примечания  
 Эта функция только после вызова [DoModal](#domodal) возвращает **IDOK**.  
  
 Дополнительные сведения см. в разделе [OLEUICHANGESOURCE](http://msdn.microsoft.com/library/windows/desktop/ms682160) Структура пакета SDK для Windows.  
  
## <a name="see-also"></a>См. также  
 [Класс COleDialog](../../mfc/reference/coledialog-class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Класс COleDialog](../../mfc/reference/coledialog-class.md)
