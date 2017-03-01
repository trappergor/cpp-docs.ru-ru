---
title: "Класс COlePropertiesDialog | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- COlePropertiesDialog
dev_langs:
- C++
helpviewer_keywords:
- OLE Object Properties dialog box
- Object Properties dialog box
- dialog boxes, OLE
- OLE documents, modifying properties
- property pages, OLE
- COlePropertiesDialog class
ms.assetid: a54dbc89-1447-4329-bd01-00e98ec9e935
caps.latest.revision: 23
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
ms.openlocfilehash: 0c07766bca6bbc546f877e10255d80bd388d30d7
ms.lasthandoff: 02/24/2017

---
# <a name="colepropertiesdialog-class"></a>Класс COlePropertiesDialog
Инкапсулирует стандартное диалоговое окно свойств объекта OLE Windows.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class COlePropertiesDialog : public COleDialog  
```  
  
## <a name="members"></a>Члены  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[COlePropertiesDialog::COlePropertiesDialog](#colepropertiesdialog)|Создает объект `COlePropertiesDialog`.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[COlePropertiesDialog::DoModal](#domodal)|Отображает диалоговое окно и позволяет пользователю сделать выбор.|  
|[COlePropertiesDialog::OnApplyScale](#onapplyscale)|Вызывается инфраструктурой при изменении масштабирования элемента документа.|  
  
### <a name="public-data-members"></a>Открытые члены данных  
  
|Имя|Описание|  
|----------|-----------------|  
|[COlePropertiesDialog::m_gp](#m_gp)|Структура, используемая для инициализации страницы «Общие» `COlePropertiesDialog` объекта.|  
|[COlePropertiesDialog::m_lp](#m_lp)|Структура, используемая для инициализации на странице «Ссылки» `COlePropertiesDialog` объекта.|  
|[COlePropertiesDialog::m_op](#m_op)|Структура, используемая для инициализации `COlePropertiesDialog` объекта.|  
|[COlePropertiesDialog::m_psh](#m_psh)|Структура, используемая для добавления дополнительных пользовательских свойств.|  
|[COlePropertiesDialog::m_vp](#m_vp)|Структура, используемая для настройки на странице «Представление» `COlePropertiesDialog` объекта.|  
  
## <a name="remarks"></a>Примечания  
 Общие диалоговые окна свойств объекта OLE предоставляют простой способ отображения и изменения свойств элемента документа OLE в соответствии со стандартами Windows. В частности, эти свойства включают сведения о файле, представленной элементом документа параметры отображения значка и масштабирование и информацией на ссылка элемента (если элемент связан).  
  
 Для использования `COlePropertiesDialog` объекта, сначала создайте объект с помощью `COlePropertiesDialog` конструктор. После отправки окно вызова `DoModal` функции-члена для отображения диалогового окна и разрешить пользователю изменять любые свойства элемента. `DoModal`Возвращает, выбрал ли пользователь ОК ( **IDOK**) или Отмена ( **IDCANCEL**) кнопки. Помимо кнопки OK и Отмена существует кнопку Применить. Когда пользователь выбирает применить, любые изменения, внесенные в свойства элемента документа применяются к элементу и его изображение обновляется автоматически, но остается активным.  
  
 [M_psh](#m_psh) член данных — указатель на **PROPSHEETHEADER** структуры и в большинстве случаев не потребуется доступ к явным образом. Единственное исключение — когда нужны дополнительные страницы свойств за пределы страницы Общие представления и ссылки по умолчанию. В этом случае можно изменить `m_psh` данные-член для включения пользовательских страниц перед вызовом метода `DoModal` функции-члена.  
  
 Дополнительные сведения о диалоговых окнах OLE см. в статье [диалоговые окна в OLE](../../mfc/dialog-boxes-in-ole.md).  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CDialog](../../mfc/reference/cdialog-class.md)  
  
 [CCommonDialog](../../mfc/reference/ccommondialog-class.md)  
  
 [COleDialog](../../mfc/reference/coledialog-class.md)  
  
 `COlePropertiesDialog`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxodlgs.h  
  
##  <a name="a-namecolepropertiesdialoga--colepropertiesdialogcolepropertiesdialog"></a><a name="colepropertiesdialog"></a>COlePropertiesDialog::COlePropertiesDialog  
 Создает объект `COlePropertiesDialog`.  
  
```  
COlePropertiesDialog(
    COleClientItem* pItem,  
    UINT nScaleMin = 10,  
    UINT nScaleMax = 500,  
    CWnd* pParentWnd = NULL);
```  
  
### <a name="parameters"></a>Параметры  
 `pItem`  
 Указатель на элемент документа, свойства которого осуществляется.  
  
 *nScaleMin*  
 Минимальный масштаб в процентах для изображения элемента документа.  
  
 *nScaleMax*  
 Максимальный масштаб в процентах для изображения элемента документа.  
  
 `pParentWnd`  
 Указатель на родительский или владельца диалогового окна.  
  
### <a name="remarks"></a>Примечания  
 Производных классов общих диалоговых окон свойств объекта OLE из `COlePropertiesDialog` для реализации масштабирования для элементов документа. Все диалоговые окна реализуется экземпляр этого класса не будет поддерживать масштабирование элемента документа.  
  
 По умолчанию стандартным диалоговым окном свойств объекта OLE имеет три страницы по умолчанию:  
  
-   Общие  
  
     Эта страница содержит системные сведения для файла, представленной элементом выбранного документа. На этой странице пользователя можно преобразовать выбранный элемент в другой тип.  
  
-   Просмотр  
  
     На этой странице содержатся параметры для отображения элемента, изменение значка и изменение масштабирования изображения.  
  
-   Ссылка  
  
     На этой странице содержатся параметры для изменения расположения связанного элемента и обновление связанного элемента. На этой странице пользователь может разорвать связь выбранного элемента.  
  
 Чтобы добавить страницы, не реализованных по умолчанию, измените [m_psh](#m_psh) переменную-член перед выходом из конструктора вашей `COlePropertiesDialog`-производного класса. Это расширенную реализацию `COlePropertiesDialog` конструктора.  
  
##  <a name="a-namedomodala--colepropertiesdialogdomodal"></a><a name="domodal"></a>COlePropertiesDialog::DoModal  
 Вызовите эту функцию-член для отображения общих свойств объекта OLE диалоговым окном Windows и позволяет пользователю просматривать и изменять различные свойства элемента документа.  
  
```  
virtual INT_PTR DoModal();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 **IDOK** или **IDCANCEL** Если успешно; в противном случае — 0. **IDOK** и **IDCANCEL** константы, которые указывают, выбрал ли пользователь кнопку OK или "Отмена".  
  
 Если **IDCANCEL** возвращается, можно вызвать Windows [CommDlgExtendedError](http://msdn.microsoft.com/library/windows/desktop/ms646916) функции, чтобы определить, произошла ли ошибка.  
  
##  <a name="a-namemgpa--colepropertiesdialogmgp"></a><a name="m_gp"></a>COlePropertiesDialog::m_gp  
 Структура типа [OLEUIGNRLPROPS](http://msdn.microsoft.com/library/windows/desktop/ms687297), которое используется для инициализации страница «Общие» диалогового окна свойств объекта OLE.  
  
```  
OLEUIGNRLPROPS m_gp;  
```  
  
### <a name="remarks"></a>Примечания  
 На этой странице показан тип и размер внедрения и позволяет пользователю доступ к диалоговому окну Convert. Эта страница показывает конечный объект ссылки Если объект является ссылкой.  
  
 Дополнительные сведения о **OLEUIGNRLPROPS** структуры см. в разделе [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-namemlpa--colepropertiesdialogmlp"></a><a name="m_lp"></a>COlePropertiesDialog::m_lp  
 Структура типа [OLEUILINKPROPS](http://msdn.microsoft.com/library/windows/desktop/ms680735), которое используется для инициализации ссылки страницы диалогового окна свойств объекта OLE.  
  
```  
OLEUILINKPROPS m_lp;  
```  
  
### <a name="remarks"></a>Примечания  
 Эта страница показывает расположение связанного элемента и позволяет пользователю обновлять или прервать, ссылку на элемент.  
  
 Дополнительные сведения о **OLEUILINKPROPS** структуры см. в разделе [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-namemopa--colepropertiesdialogmop"></a><a name="m_op"></a>COlePropertiesDialog::m_op  
 Структура типа [OLEUIOBJECTPROPS](http://msdn.microsoft.com/library/windows/desktop/ms687199), которое используется для инициализации стандартным диалоговым окном свойств объекта OLE.  
  
```  
OLEUIOBJECTPROPS m_op;  
```  
  
### <a name="remarks"></a>Примечания  
 Эта структура содержит элементы, используемые для инициализации страницы Общие, связи и представления.  
  
 Дополнительные сведения см. в разделе **OLEUIOBJECTPROPS** и [OLEUILINKPROPS](http://msdn.microsoft.com/library/windows/desktop/ms680735) структур в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-namempsha--colepropertiesdialogmpsh"></a><a name="m_psh"></a>COlePropertiesDialog::m_psh  
 Структура типа [PROPSHEETHEADER](http://msdn.microsoft.com/library/windows/desktop/bb774546), члены которого хранения характеристики объекта диалогового окна.  
  
```  
PROPSHEETHEADER m_psh;  
```  
  
### <a name="remarks"></a>Примечания  
 После построения `COlePropertiesDialog` объекта, можно использовать `m_psh` для задания различных аспектов диалоговым окном перед вызовом метода `DoModal` функции-члена.  
  
 Если изменить `m_psh` член данных напрямую, переопределяют любое поведение по умолчанию.  
  
 Дополнительные сведения о **PROPSHEETHEADER** структуры см. в разделе [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-namemvpa--colepropertiesdialogmvp"></a><a name="m_vp"></a>COlePropertiesDialog::m_vp  
 Структура типа [OLEUIVIEWPROPS](http://msdn.microsoft.com/library/windows/desktop/ms693751), которое используется для инициализации странице диалогового окна свойств объекта OLE.  
  
```  
OLEUIVIEWPROPS m_vp;  
```  
  
### <a name="remarks"></a>Примечания  
 Эта страница позволяет пользователю переключаться между «содержимое» и «культовой» представления объекта и изменения масштаба в контейнере. Также позволяет пользователю доступ к диалоговому окну сменить значок, если объект отображается как значок.  
  
 Дополнительные сведения о **OLEUIVIEWPROPS** структуры см. в разделе [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-nameonapplyscalea--colepropertiesdialogonapplyscale"></a><a name="onapplyscale"></a>COlePropertiesDialog::OnApplyScale  
 Вызывается платформой, если изменилось значение масштабирования и выбран ОК или применить.  
  
```  
virtual BOOL OnApplyScale(
    COleClientItem* pItem,  
    int nCurrentScale,  
    BOOL bRelativeToOrig);
```  
  
### <a name="parameters"></a>Параметры  
 `pItem`  
 Указатель на элемент документа, свойства которого осуществляется.  
  
 `nCurrentScale`  
 Числовое значение шкалы диалогового окна.  
  
 *bRelativeToOrig*  
 Указывает, масштабирование, применимо ли исходный размер элемента документа.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если обработанное; в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Реализация по умолчанию не выполняет никаких действий. Необходимо переопределить функцию масштабирования элементов управления.  
  
> [!NOTE]
>  Перед отображением стандартным диалоговым окном свойств объекта OLE, платформа вызывает эту функцию с **NULL** для `pItem` и 1 для `nCurrentScale`. Это делается для определения, должен быть включен масштабирования элементов управления.  
  
## <a name="see-also"></a>См. также  
 [Пример MFC Кр](../../visual-cpp-samples.md)   
 [Класс COleDialog](../../mfc/reference/coledialog-class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Класс COleDialog](../../mfc/reference/coledialog-class.md)   
 [CPropertyPage-класс](../../mfc/reference/cpropertypage-class.md)

