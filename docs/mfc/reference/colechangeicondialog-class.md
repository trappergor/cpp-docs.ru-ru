---
title: "Класс COleChangeIconDialog | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- COleChangeIconDialog
- AFXODLGS/COleChangeIconDialog
- AFXODLGS/COleChangeIconDialog::COleChangeIconDialog
- AFXODLGS/COleChangeIconDialog::DoChangeIcon
- AFXODLGS/COleChangeIconDialog::DoModal
- AFXODLGS/COleChangeIconDialog::GetIconicMetafile
- AFXODLGS/COleChangeIconDialog::m_ci
dev_langs:
- C++
helpviewer_keywords:
- OLE dialog boxes, Change Icon
- OLE Change Icon dialog box
- dialog boxes, OLE
- COleChangeIconDialog class
- Change Icon dialog box
ms.assetid: 8d6e131b-ddbb-4dff-a432-f239efda8e3d
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
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: 07dfd7995bbbdb0f52f55dceedc318d8d702111b
ms.contentlocale: ru-ru
ms.lasthandoff: 02/24/2017

---
# <a name="colechangeicondialog-class"></a>Класс COleChangeIconDialog
Используется для диалогового окна OLE "Изменить значок".  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class COleChangeIconDialog : public COleDialog  
```  
  
## <a name="members"></a>Члены  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[COleChangeIconDialog::COleChangeIconDialog](#colechangeicondialog)|Создает объект `COleChangeIconDialog`.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[COleChangeIconDialog::DoChangeIcon](#dochangeicon)|Выполняет изменения, указанные в диалоговом окне.|  
|[COleChangeIconDialog::DoModal](#domodal)|Отображение диалогового окна OLE 2 изменить значок.|  
|[COleChangeIconDialog::GetIconicMetafile](#geticonicmetafile)|Возвращает дескриптор метафайла, связанные со значками форме этого элемента.|  
  
### <a name="public-data-members"></a>Открытые члены данных  
  
|Имя|Описание|  
|----------|-----------------|  
|[COleChangeIconDialog::m_ci](#m_ci)|Структура, которая управляет поведением диалогового окна.|  
  
## <a name="remarks"></a>Примечания  
 Создание объекта класса `COleChangeIconDialog` когда необходимо вызвать это диалоговое окно предназначено. После `COleChangeIconDialog` объект был создан, можно использовать [m_ci](#m_ci) структуры для инициализации значения или состояния элементов управления в диалоговом окне. `m_ci` Структуры имеет тип **OLEUICHANGEICON**. Дополнительные сведения об использовании этого класса диалогового окна в разделе [DoModal](#domodal) функции-члена.  
  
 Дополнительные сведения см. в разделе [OLEUICHANGEICON](http://msdn.microsoft.com/library/windows/desktop/ms680098) в структуре [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 Дополнительные сведения о диалоговых окнах OLE конкретных см. в статье [диалоговые окна в OLE](../../mfc/dialog-boxes-in-ole.md).  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CDialog](../../mfc/reference/cdialog-class.md)  
  
 [CCommonDialog](../../mfc/reference/ccommondialog-class.md)  
  
 [COleDialog](../../mfc/reference/coledialog-class.md)  
  
 `COleChangeIconDialog`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxodlgs.h  
  
##  <a name="colechangeicondialog"></a>COleChangeIconDialog::COleChangeIconDialog  
 Эта функция создает только `COleChangeIconDialog` объекта.  
  
```  
explicit COleChangeIconDialog(
    COleClientItem* pItem,  
    DWORD dwFlags = CIF_SELECTCURRENT,  
    CWnd* pParentWnd = NULL);
```  
  
### <a name="parameters"></a>Параметры  
 `pItem`  
 Указывает элемент для преобразования.  
  
 `dwFlags`  
 Создание флаг, который содержит любое количество следующих значений в сочетании с помощью побитового- or -оператор:  
  
- **CIF_SELECTCURRENT** указывает, что текущий переключатель выберет изначально при вызове диалогового. Это значение по умолчанию.  
  
- **CIF_SELECTDEFAULT** указывает, что по умолчанию переключатель выберет изначально при вызове диалоговое окно.  
  
- **CIF_SELECTFROMFILE** указывает, что переключатель из файла выберет изначально при вызове диалогового.  
  
- **CIF_SHOWHELP** задает отображение кнопки справки при вызове диалоговое окно.  
  
- **CIF_USEICONEXE** указывает, что значок следует извлечь из исполняемый файл, указанный в **szIconExe** поле [m_ci](#m_ci) вместо зависят от типа. Это облегчает внедрение или связывание с файлами, отличных от OLE.  
  
 `pParentWnd`  
 Указывает на объект окна родительского или владелец (типа `CWnd`), которому принадлежит объект диалогового окна. Если это **NULL**, родительского окна окно будет присвоено главного окна приложения.  
  
### <a name="remarks"></a>Примечания  
 Чтобы открыть диалоговое окно, вызовите [DoModal](#domodal) функции.  
  
 Дополнительные сведения см. в разделе [OLEUICHANGEICON](http://msdn.microsoft.com/library/windows/desktop/ms680098) в структуре [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="dochangeicon"></a>COleChangeIconDialog::DoChangeIcon  
 Вызывайте эту функцию, чтобы изменить значок, представляющий элемент, выбранный в диалоговом окне после [DoModal](#domodal) возвращает **IDOK**.  
  
```  
BOOL DoChangeIcon(COleClientItem* pItem);
```  
  
### <a name="parameters"></a>Параметры  
 `pItem`  
 Указывает на изменение, значок элемента.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если изменение выполнено успешно; в противном случае — 0.  
  
##  <a name="domodal"></a>COleChangeIconDialog::DoModal  
 Эта функция вызывается для отображения диалогового окна OLE изменить значок.  
  
```  
virtual INT_PTR DoModal();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Состояние завершения для диалогового окна. Одно из следующих значений:  
  
- **IDOK** Если успешно откроется диалоговое окно.  
  
- **IDCANCEL** Если пользователь отменил диалоговое окно.  
  
- **IDABORT** произошла ошибка. Если **IDABORT** будет возвращен, вызовите `COleDialog::GetLastError` функции-члена для получения дополнительных сведений о типе возникшей ошибки. Список возможных ошибок см. в разделе [OleUIChangeIcon](http://msdn.microsoft.com/library/windows/desktop/ms688307) работать в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="remarks"></a>Примечания  
 Если требуется инициализировать различные диалоговыми окнами, задав члены [m_ci](#m_ci) структуры, это следует сделать до вызова метода `DoModal`, но после создания объекта диалогового окна.  
  
 Если `DoModal` возвращает **IDOK**, можно вызвать другой член функции для получения параметров или данных, введенных пользователем в диалоговом окне.  
  
##  <a name="geticonicmetafile"></a>COleChangeIconDialog::GetIconicMetafile  
 Эта функция вызывается для получения дескриптора метафайла, содержит символическое аспектом выбранного элемента.  
  
```  
HGLOBAL GetIconicMetafile() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Дескриптор метафайла, содержащий значками аспектом новый значок, если диалоговое окно было закрыто, выбрав **ОК**; в противном случае, значок, как оно было отображения диалогового окна.  
  
##  <a name="m_ci"></a>COleChangeIconDialog::m_ci  
 Структура типа **OLEUICHANGEICON** используется для управления поведением диалоговое окно Изменить значок.  
  
```  
OLEUICHANGEICON m_ci;  
```  
  
### <a name="remarks"></a>Примечания  
 Можно изменить члены этой структуры, либо непосредственно, либо с помощью функций-членов.  
  
 Дополнительные сведения см. в разделе [OLEUICHANGEICON](http://msdn.microsoft.com/library/windows/desktop/ms680098) в структуре [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
## <a name="see-also"></a>См. также  
 [Класс COleDialog](../../mfc/reference/coledialog-class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Класс COleDialog](../../mfc/reference/coledialog-class.md)

