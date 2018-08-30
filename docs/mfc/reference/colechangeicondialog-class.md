---
title: Класс COleChangeIconDialog | Документация Майкрософт
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
ms.openlocfilehash: 089fe435c86b524acc41ba528452d93032d1b1a4
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/29/2018
ms.locfileid: "43214497"
---
# <a name="colechangeicondialog-class"></a>Класс COleChangeIconDialog
Используется для диалогового окна OLE "Изменить значок".  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class COleChangeIconDialog : public COleDialog  
```  
  
## <a name="members"></a>Участники  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[COleChangeIconDialog::COleChangeIconDialog](#colechangeicondialog)|Создает объект `COleChangeIconDialog`.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[COleChangeIconDialog::DoChangeIcon](#dochangeicon)|Выполняет изменения, указанные в диалоговом окне.|  
|[COleChangeIconDialog::DoModal](#domodal)|Отображает диалоговое окно OLE 2 Смена значка.|  
|[COleChangeIconDialog::GetIconicMetafile](#geticonicmetafile)|Получает дескриптор метафайла, связанных с формой, преобразованного в значок этого элемента.|  
  
### <a name="public-data-members"></a>Открытые члены данных  
  
|Имя|Описание:|  
|----------|-----------------|  
|[COleChangeIconDialog::m_ci](#m_ci)|Структура, которая управляет поведением окна.|  
  
## <a name="remarks"></a>Примечания  
 Создайте объект класса `COleChangeIconDialog` при необходимости вызвать это диалоговое окно. После `COleChangeIconDialog` объект был создан, можно использовать [m_ci](#m_ci) структуры для инициализации значения или состояния элементов управления в диалоговом окне. `m_ci` Структуры имеет тип OLEUICHANGEICON. Дополнительные сведения об использовании этого класса диалогового окна см. в разделе [DoModal](#domodal) функция-член.  
  
 Дополнительные сведения см. в разделе [OLEUICHANGEICON](/windows/desktop/api/oledlg/ns-oledlg-tagoleuichangeicona) структуры в пакете Windows SDK.  
  
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
 *pItem*  
 Указывает элемент для преобразования.  
  
 *dwFlags*  
 Создание флаг, который содержит любое количество следующих значений в сочетании с помощью побитовой операции- или оператор:  
  
- CIF_SELECTCURRENT указывает, что переключатель «текущей» будет выбран при вызове диалоговое окно. Это значение по умолчанию.  
  
- CIF_SELECTDEFAULT указывает, что переключатель по умолчанию будет выбран при вызове диалоговое окно.  
  
- CIF_SELECTFROMFILE указывает, что переключатель из файла будет выбран при вызове диалоговое окно.  
  
- CIF_SHOWHELP указывает, что при вызове диалоговом окне будет отображаться кнопку "Справка".  
  
- CIF_USEICONEXE указывает, что значок должен быть извлечен из исполняемый файл, указанный в `szIconExe` поле [m_ci](#m_ci) вместо извлечения из типа. Это полезно для внедрения или связи с файлами, отличных от OLE.  
  
 *pParentWnd*  
 Указывает на объект окна родительский объект или владельца (типа `CWnd`), которому принадлежит объект диалогового окна. Если это значение NULL, родительского окна окно будет присвоено главного окна приложения.  
  
### <a name="remarks"></a>Примечания  
 Чтобы отобразить диалоговое окно, вызовите [DoModal](#domodal) функции.  
  
 Дополнительные сведения см. в разделе [OLEUICHANGEICON](/windows/desktop/api/oledlg/ns-oledlg-tagoleuichangeicona) структуры в пакете Windows SDK.  
  
##  <a name="dochangeicon"></a>  COleChangeIconDialog::DoChangeIcon  
 Вызывайте эту функцию, чтобы изменить значок, представляющий элемент для выбранного в диалоговом окне после [DoModal](#domodal) возвращает IDOK.  
  
```  
BOOL DoChangeIcon(COleClientItem* pItem);
```  
  
### <a name="parameters"></a>Параметры  
 *pItem*  
 Указывает элемент меняется, значок.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если изменение выполнено успешно; в противном случае 0.  
  
##  <a name="domodal"></a>  COleChangeIconDialog::DoModal  
 Вызывайте эту функцию для отображения диалогового окна OLE Смена значка.  
  
```  
virtual INT_PTR DoModal();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Состояние завершения для диалогового окна. Одно из следующих значений:  
  
- IDOK, если было успешно отображено диалоговое окно.  
  
- IDCANCEL, если пользователь отменил диалоговое окно.  
  
- IDABORT, если произошла ошибка. Если возвращается IDABORT, вызовите `COleDialog::GetLastError` функция-член для получения дополнительных сведений о типе возникшей ошибки. Список возможных ошибок, см. в разделе [OleUIChangeIcon](/windows/desktop/api/oledlg/nf-oledlg-oleuichangeicona) функции в пакете Windows SDK.  
  
### <a name="remarks"></a>Примечания  
 Если вы хотите инициализировать различных диалоговых путем определения участников [m_ci](#m_ci) структуры, это следует сделать до вызова метода `DoModal`, но после создания объекта диалогового окна.  
  
 Если `DoModal` возвращает IDOK, можно вызывать другой член функции для получения параметров или данных, введенных пользователем в диалоговом окне.  
  
##  <a name="geticonicmetafile"></a>  COleChangeIconDialog::GetIconicMetafile  
 Вызывайте эту функцию для получения дескриптора метафайл, содержащий аспект, преобразованного в значок выбранного элемента.  
  
```  
HGLOBAL GetIconicMetafile() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Дескриптор метафайла, содержащий преобразованные в значки аспектом значок "Создать", в том случае, если диалоговое окно было закрыть, выбрав **ОК**; в противном случае этот значок как она была до диалоговое окно было отображено.  
  
##  <a name="m_ci"></a>  COleChangeIconDialog::m_ci  
 Структура типа OLEUICHANGEICON используется для управления поведением диалогового окна "Смена значка".  
  
```  
OLEUICHANGEICON m_ci;  
```  
  
### <a name="remarks"></a>Примечания  
 Члены этой структуры можно изменить напрямую или с помощью функций-членов.  
  
 Дополнительные сведения см. в разделе [OLEUICHANGEICON](/windows/desktop/api/oledlg/ns-oledlg-tagoleuichangeicona) структуры в пакете Windows SDK.  
  
## <a name="see-also"></a>См. также  
 [Класс COleDialog](../../mfc/reference/coledialog-class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Класс COleDialog](../../mfc/reference/coledialog-class.md)
