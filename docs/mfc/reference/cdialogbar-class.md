---
title: CDialogBar-класс | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CDialogBar
- AFXEXT/CDialogBar
- AFXEXT/CDialogBar::CDialogBar
- AFXEXT/CDialogBar::Create
dev_langs:
- C++
helpviewer_keywords:
- CDialogBar [MFC], CDialogBar
- CDialogBar [MFC], Create
ms.assetid: da2f7a30-970c-44e3-87f0-6094bd002cab
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 7dbb2d8202e9b87d2825b7d40a0dde4323246aa0
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33366718"
---
# <a name="cdialogbar-class"></a>CDialogBar-класс
Предоставляет функциональные возможности немодального диалогового окна Windows на панели элементов управления.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CDialogBar : public CControlBar  
```  
  
## <a name="members"></a>Участники  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CDialogBar::CDialogBar](#cdialogbar)|Создает объект `CDialogBar`.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CDialogBar::Create](#create)|Создает диалоговую панель Windows и прикрепляет его к `CDialogBar` объекта.|  
  
## <a name="remarks"></a>Примечания  
 Диалоговая панель напоминает диалоговое окно, в том, что он содержит стандартные элементы управления Windows, которые пользователь переместиться между. Другой аспект имеет создания шаблона диалогового окна для диалоговой панели представления.  
  
 Создание и использование диалоговой панели аналогично созданию и использованию `CFormView` объекта. Во-первых, используйте [редактор диалоговых окон](../../windows/dialog-editor.md) определить шаблон диалогового окна со стилем **WS_CHILD** и не другой стиль. Шаблон не должен иметь стиль **WS_VISIBLE**. В коде приложения вызовите конструктор для создания `CDialogBar` объекта, а затем вызвать **создать** для создания окна диалоговой панели и присоединить его к `CDialogBar` объекта.  
  
 Дополнительные сведения о `CDialogBar`, см. в статье [диалоговые панели](../../mfc/dialog-bars.md) и [Технические заметки 31](../../mfc/tn031-control-bars.md), панелей элементов управления.  
  
> [!NOTE]
>  В текущем выпуске `CDialogBar` не может размещать элементы управления Windows Forms. Дополнительные сведения об элементах управления Windows Forms в Visual C++ см. в разделе [с помощью пользовательского элемента управления формы Windows в MFC](../../dotnet/using-a-windows-form-user-control-in-mfc.md).  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CControlBar](../../mfc/reference/ccontrolbar-class.md)  
  
 `CDialogBar`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxext.h  
  
##  <a name="cdialogbar"></a>  CDialogBar::CDialogBar  
 Создает объект `CDialogBar`.  
  
```  
CDialogBar();
```  
  
##  <a name="create"></a>  CDialogBar::Create  
 Загружает ресурса шаблона диалогового окна, указанного `lpszTemplateName` или `nIDTemplate`, создает окно диалоговая панель, задает его стиль и связывает его с `CDialogBar` объекта.  
  
```  
virtual BOOL Create(
    CWnd* pParentWnd,  
    LPCTSTR lpszTemplateName,  
    UINT nStyle,  
    UINT nID);

 
virtual BOOL Create(
    CWnd* pParentWnd,  
    UINT nIDTemplate,  
    UINT nStyle,  
    UINT nID);
```  
  
### <a name="parameters"></a>Параметры  
 `pParentWnd`  
 Указатель на родительский `CWnd` объекта.  
  
 `lpszTemplateName`  
 Указатель на имя `CDialogBar` объекта шаблона ресурсов диалогового окна.  
  
 `nStyle`  
 Стиль панели инструментов. Существуют следующие стили дополнительных инструментов поддерживается:  
  
- `CBRS_TOP` Строка управления находится в верхней части окна фрейма.  
  
- `CBRS_BOTTOM` Панель элементов управления — в нижней части окна фрейма.  
  
- `CBRS_NOALIGN` Панель элементов управления не меняет свое положение при изменении размеров родительского.  
  
- `CBRS_TOOLTIPS` Панель элементов управления отображаются всплывающие подсказки.  
  
- **CBRS_SIZE_DYNAMIC** панели элементов управления является динамическим.  
  
- **CBRS_SIZE_FIXED** фиксированной панель элементов управления.  
  
- **CBRS_FLOATING** плавающей панели элементов управления.  
  
- `CBRS_FLYBY` Строка состояния отображает сведения о кнопке.  
  
- **CBRS_HIDE_INPLACE** панели элементов управления не отображается для пользователя.  
  
 `nID`  
 Идентификатор элемента управления панели диалогового окна.  
  
 `nIDTemplate`  
 Идентификатор ресурса `CDialogBar` объекта шаблона диалогового окна.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имеет ненулевое значение в случае успешного выполнения, иначе — 0.  
  
### <a name="remarks"></a>Примечания  
 При указании `CBRS_TOP` или `CBRS_BOTTOM` стиль выравнивания диалоговая панель ширина, окна фрейма, а его высота была, ресурс, указанный параметром `nIDTemplate`. При указании `CBRS_LEFT` или `CBRS_RIGHT` стиль выравнивания диалоговая панель высота, окна фрейма, а его ширину, представляет ресурс, указанный параметром `nIDTemplate`.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCMessageMaps#13](../../mfc/reference/codesnippet/cpp/cdialogbar-class_1.cpp)]  
  
## <a name="see-also"></a>См. также  
 [Пример MFC CTRLBARS](../../visual-cpp-samples.md)   
 [CControlBar-класс](../../mfc/reference/ccontrolbar-class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Класс CFormView](../../mfc/reference/cformview-class.md)   
 [Класс CControlBar](../../mfc/reference/ccontrolbar-class.md)
