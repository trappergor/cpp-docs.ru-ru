---
title: Класс COleChangeIconDialog | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
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
- COleChangeIconDialog [MFC], COleChangeIconDialog
- COleChangeIconDialog [MFC], DoChangeIcon
- COleChangeIconDialog [MFC], DoModal
- COleChangeIconDialog [MFC], GetIconicMetafile
- COleChangeIconDialog [MFC], m_ci
ms.assetid: 8d6e131b-ddbb-4dff-a432-f239efda8e3d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: b675cfd635fd4dea962c30605072beec1545dda1
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="colechangeicondialog-class"></a>Класс COleChangeIconDialog
Используется для диалогового окна OLE "Изменить значок".  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class COleChangeIconDialog : public COleDialog  
```  
  
## <a name="members"></a>Участники  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[COleChangeIconDialog::COleChangeIconDialog](#colechangeicondialog)|Создает объект `COleChangeIconDialog`.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[COleChangeIconDialog::DoChangeIcon](#dochangeicon)|Выполняет изменения, указанные в диалоговом окне.|  
|[COleChangeIconDialog::DoModal](#domodal)|Отображение диалогового окна OLE 2 изменить значок.|  
|[COleChangeIconDialog::GetIconicMetafile](#geticonicmetafile)|Возвращает дескриптор метафайла, связанных с формой, преобразованного в значок этого элемента.|  
  
### <a name="public-data-members"></a>Открытые члены данных  
  
|Имя|Описание|  
|----------|-----------------|  
|[COleChangeIconDialog::m_ci](#m_ci)|Структура, которая управляет поведением окна.|  
  
## <a name="remarks"></a>Примечания  
 Создание объекта класса `COleChangeIconDialog` при необходимости вызовите данным диалоговым окном. После `COleChangeIconDialog` объект был создан, можно использовать [m_ci](#m_ci) структуры для инициализации значения или состояния элементов управления в диалоговом окне. `m_ci` Структуры имеет тип **OLEUICHANGEICON**. Дополнительные сведения об использовании этого класса диалогового окна см. в разделе [DoModal](#domodal) функции-члена.  
  
 Дополнительные сведения см. в разделе [OLEUICHANGEICON](http://msdn.microsoft.com/library/windows/desktop/ms680098) структуры в Windows SDK.  
  
 Дополнительные сведения о конкретных OLE диалоговым окнам см. в статье [диалоговые окна в OLE](../../mfc/dialog-boxes-in-ole.md).  
  
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
  
##  <a name="colechangeicondialog"></a>  COleChangeIconDialog::COleChangeIconDialog  
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
 Создание флаг, который содержит произвольное количество следующие значения, объединенные с помощью битовой операции- или оператор:  
  
- **CIF_SELECTCURRENT** указывает, что текущей переключатель выбирается изначально при вызове диалоговое окно. Это значение по умолчанию.  
  
- **CIF_SELECTDEFAULT** указывает, что переключатель по умолчанию выбирается изначально при вызове диалоговым окном.  
  
- **CIF_SELECTFROMFILE** указывает, что переключатель из файла будут выбираться изначально при вызове диалоговым окном.  
  
- **CIF_SHOWHELP** задает отображение кнопки справки при вызове диалоговым окном.  
  
- **CIF_USEICONEXE** указывает, что значок должно быть извлечено из исполняемый файл, указанный в **szIconExe** поле [m_ci](#m_ci) вместо извлечения из типа. Это полезно для внедрения или связывания для файлов, отличных от OLE.  
  
 `pParentWnd`  
 Указывает на объект window родительского или владелец (типа `CWnd`), которому принадлежит объект диалогового окна. Если это **NULL**, родительское окно диалогового окна будет присвоено главного окна приложения.  
  
### <a name="remarks"></a>Примечания  
 Чтобы открыть диалоговое окно, вызовите [DoModal](#domodal) функции.  
  
 Дополнительные сведения см. в разделе [OLEUICHANGEICON](http://msdn.microsoft.com/library/windows/desktop/ms680098) структуры в Windows SDK.  
  
##  <a name="dochangeicon"></a>  COleChangeIconDialog::DoChangeIcon  
 Вызывайте эту функцию, чтобы изменить значок, представляющий элемент, выбранный в диалоговом окне после [DoModal](#domodal) возвращает **IDOK**.  
  
```  
BOOL DoChangeIcon(COleClientItem* pItem);
```  
  
### <a name="parameters"></a>Параметры  
 `pItem`  
 Указывает на изменение, значок элемента.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если изменение выполнено успешно; в противном случае — 0.  
  
##  <a name="domodal"></a>  COleChangeIconDialog::DoModal  
 Эта функция вызывается для отображения диалогового окна OLE изменить значок.  
  
```  
virtual INT_PTR DoModal();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Состояние завершения для диалогового окна. Одно из следующих значений:  
  
- **IDOK** Если успешно откроется диалоговое окно.  
  
- **IDCANCEL** Если пользователь отменил это диалоговое окно.  
  
- **IDABORT** Если произошла ошибка. Если **IDABORT** будет возвращен, вызовите `COleDialog::GetLastError` функции-члена для получения дополнительных сведений о типе возникшей ошибки. Для получения списка возможных ошибок [OleUIChangeIcon](http://msdn.microsoft.com/library/windows/desktop/ms688307) функции в Windows SDK.  
  
### <a name="remarks"></a>Примечания  
 Если требуется инициализировать различные элементы управления диалоговых окон, задав члены [m_ci](#m_ci) структуры, это следует сделать до вызова метода `DoModal`, но после создания объекта диалогового окна.  
  
 Если `DoModal` возвращает **IDOK**, можно вызывать другой член функции для получения параметров или сведения, введенных пользователем в диалоговом окне.  
  
##  <a name="geticonicmetafile"></a>  COleChangeIconDialog::GetIconicMetafile  
 Эта функция вызывается для получения дескриптора метафайла, содержащий аспект, преобразованного в значок выбранного элемента.  
  
```  
HGLOBAL GetIconicMetafile() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Дескриптор метафайла, содержащий аспект, преобразованного в значок нового значка, если диалоговое окно было отклонено, выбрав **ОК**; в противном случае значок, как оно было перед отображается диалоговое окно.  
  
##  <a name="m_ci"></a>  COleChangeIconDialog::m_ci  
 Структура типа **OLEUICHANGEICON** используется для управления поведением диалогового окна "Изменить значок".  
  
```  
OLEUICHANGEICON m_ci;  
```  
  
### <a name="remarks"></a>Примечания  
 Члены этой структуры можно изменить напрямую или с помощью функций-членов.  
  
 Дополнительные сведения см. в разделе [OLEUICHANGEICON](http://msdn.microsoft.com/library/windows/desktop/ms680098) структуры в Windows SDK.  
  
## <a name="see-also"></a>См. также  
 [Класс COleDialog](../../mfc/reference/coledialog-class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Класс COleDialog](../../mfc/reference/coledialog-class.md)
