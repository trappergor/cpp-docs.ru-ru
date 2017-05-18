---
title: "Класс CDragListBox | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CDragListBox
- AFXCMN/CDragListBox
- AFXCMN/CDragListBox::CDragListBox
- AFXCMN/CDragListBox::BeginDrag
- AFXCMN/CDragListBox::CancelDrag
- AFXCMN/CDragListBox::Dragging
- AFXCMN/CDragListBox::DrawInsert
- AFXCMN/CDragListBox::Dropped
- AFXCMN/CDragListBox::ItemFromPt
dev_langs:
- C++
helpviewer_keywords:
- drag list box [C++]
- dragging list items
- CDragListBox class
- Windows [C++], list boxes
- list boxes
ms.assetid: fee20b42-60ae-4aa9-83f9-5a3d9b96e33b
caps.latest.revision: 24
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
ms.sourcegitcommit: 4fafe461008e3545243d693e0d9e34acd57163e0
ms.openlocfilehash: 3010fd9a363aa1ca1c946a6fe967a7ba415649d4
ms.contentlocale: ru-ru
ms.lasthandoff: 02/24/2017

---
# <a name="cdraglistbox-class"></a>Класс CDragListBox
Помимо предоставления функциональных возможностей списка Windows, `CDragListBox` класс позволяет пользователю перемещать элементы списка, такие как имена файлов, в окне списка.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CDragListBox : public CListBox  
```  
  
## <a name="members"></a>Члены  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CDragListBox::CDragListBox](#cdraglistbox)|Создает объект `CDragListBox`.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CDragListBox::BeginDrag](#begindrag)|Вызывается инфраструктурой при запуске операции перетаскивания.|  
|[CDragListBox::CancelDrag](#canceldrag)|Вызывается инфраструктурой при отмене операции перетаскивания.|  
|[CDragListBox::Dragging](#dragging)|Вызывается средой во время операции перетаскивания.|  
|[CDragListBox::DrawInsert](#drawinsert)|Рисует указатель вставки, перетаскивания окна списка.|  
|[CDragListBox::Dropped](#dropped)|Вызывается платформой после элемент был удален.|  
|[CDragListBox::ItemFromPt](#itemfrompt)|Возвращает координаты перетаскиваемый элемент.|  
  
## <a name="remarks"></a>Примечания  
 Списки с возможностью позволяют упорядочить элементы в списке любым способом, наиболее полезные для них. По умолчанию поле списка будет переместить элемент в новое место в списке. Тем не менее `CDragListBox` объекты могут настраиваться для копирования элементов, а не перемещать их.  
  
 Окно списка связанных с `CDragListBox` класс не должен иметь **LBS_SORT** или **LBS_MULTIPLESELECT** стиль. Описание стили окна списка в разделе [стили списков](../../mfc/reference/list-box-styles.md).  
  
 Чтобы использовать поле со списком перетаскивания в существующем диалоговом окне приложения, добавить элемент управления списком в шаблон диалогового окна с помощью редактора диалоговых окон, а затем назначьте переменную-член (категории `Control` и тип переменной `CDragListBox`) соответствующее окно списка в шаблоне диалогового окна.  
  
 Дополнительные сведения о назначении для переменных-членов элементов управления см. в разделе [ярлык для определения переменных-членов для элементов управления диалоговых окон](../../windows/defining-member-variables-for-dialog-controls.md).  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CListBox](../../mfc/reference/clistbox-class.md)  
  
 `CDragListBox`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxcmn.h  
  
##  <a name="begindrag"></a>CDragListBox::BeginDrag  
 Вызывается методом framework, когда происходит событие, которое может начать операцию перетаскивания, например нажатия левой кнопки мыши.  
  
```  
virtual BOOL BeginDrag(CPoint pt);
```  
  
### <a name="parameters"></a>Параметры  
 `pt`  
 Объект [CPoint](../../atl-mfc-shared/reference/cpoint-class.md) объект, содержащий координаты перетаскиваемый элемент.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если перетаскивание разрешен, в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Переопределите эту функцию, если вы хотите контролировать, что происходит, когда начинается операция перетаскивания. Реализация по умолчанию захват мыши и остается в режим перетаскивания, пока пользователь не нажимает кнопку мыши влево или вправо или нажатии клавиши ESC, в какое время отменена операция перетаскивания.  
  
##  <a name="canceldrag"></a>CDragListBox::CancelDrag  
 Вызывается инфраструктурой при отмене операции перетаскивания.  
  
```  
virtual void CancelDrag(CPoint pt);
```  
  
### <a name="parameters"></a>Параметры  
 `pt`  
 Объект [CPoint](../../atl-mfc-shared/reference/cpoint-class.md) объект, содержащий координаты перетаскиваемый элемент.  
  
### <a name="remarks"></a>Примечания  
 Переопределите эту функцию для обработки специальной обработки для элемента управления поля списка.  
  
##  <a name="cdraglistbox"></a>CDragListBox::CDragListBox  
 Создает объект `CDragListBox`.  
  
```  
CDragListBox();
```  
  
##  <a name="dragging"></a>CDragListBox::Dragging  
 Вызывается инфраструктурой при перетаскиваемого элемента списка в пределах `CDragListBox` объекта.  
  
```  
virtual UINT Dragging(CPoint pt);
```  
  
### <a name="parameters"></a>Параметры  
 `pt`  
 Объект [CPoint](../../atl-mfc-shared/reference/cpoint-class.md) , содержащий свойства x и y экранные координаты курсора.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Идентификатор ресурса для отображения курсора. Возможны следующие значения:  
  
- `DL_COPYCURSOR`Указывает, что элемент не будет скопировано.  
  
- `DL_MOVECURSOR`Указывает, что элемент будет перемещен.  
  
- `DL_STOPCURSOR`Указывает, что текущего конечного места перетаскивания не принимается.  
  
### <a name="remarks"></a>Примечания  
 По умолчанию возвращает `DL_MOVECURSOR`. Эту функцию можно переопределите, чтобы обеспечить дополнительные функциональные возможности.  
  
##  <a name="drawinsert"></a>CDragListBox::DrawInsert  
 Вызывается платформой для изображения направляющих перед элементом с указанным индексом.  
  
```  
virtual void DrawInsert(int nItem);
```  
  
### <a name="parameters"></a>Параметры  
 `nItem`  
 Отсчитываемый от нуля индекс курсора.  
  
### <a name="remarks"></a>Примечания  
 Значение - 1 очищает направляющих. Переопределите эту функцию для изменения внешнего вида и поведения направляющих.  
  
##  <a name="dropped"></a>CDragListBox::Dropped  
 Вызывается инфраструктурой при удалении элемента в пределах `CDragListBox` объекта.  
  
```  
virtual void Dropped(
    int nSrcIndex,  
    CPoint pt);
```  
  
### <a name="parameters"></a>Параметры  
 *nSrcIndex*  
 Задает отсчитываемый от нуля индекс удаленной строки.  
  
 `pt`  
 Объект [CPoint](../../atl-mfc-shared/reference/cpoint-class.md) объект, содержащий координаты узла размещения.  
  
### <a name="remarks"></a>Примечания  
 Поведение по умолчанию копирует элемента списка и его данных в новое расположение, а затем удаляет исходный элемент. Переопределите эту функцию, чтобы изменить поведение по умолчанию, такие как включение копий элементы списка можно перетаскивать в другие местоположения в пределах списка.  
  
##  <a name="itemfrompt"></a>CDragListBox::ItemFromPt  
 Эту функцию для получения отсчитываемый от нуля индекс элемента списка находится на вызов `pt`.  
  
```  
int ItemFromPt(
    CPoint pt,  
    BOOL bAutoScroll = TRUE) const;  
```  
  
### <a name="parameters"></a>Параметры  
 `pt`  
 Объект [CPoint](../../atl-mfc-shared/reference/cpoint-class.md) объект, содержащий координаты точки в списке.  
  
 *bAutoScroll*  
 Ненулевое значение, если разрешена прокрутка, в противном случае — 0.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Отсчитываемый от нуля индекс элемента списка перетаскивания.  
  
## <a name="see-also"></a>См. также  
 [Пример MFC TSTCON](../../visual-cpp-samples.md)   
 [CListBox-класс](../../mfc/reference/clistbox-class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [CListBox-класс](../../mfc/reference/clistbox-class.md)

