---
title: Класс CDragListBox | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
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
- CDragListBox [MFC], CDragListBox
- CDragListBox [MFC], BeginDrag
- CDragListBox [MFC], CancelDrag
- CDragListBox [MFC], Dragging
- CDragListBox [MFC], DrawInsert
- CDragListBox [MFC], Dropped
- CDragListBox [MFC], ItemFromPt
ms.assetid: fee20b42-60ae-4aa9-83f9-5a3d9b96e33b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 34655c244f13cb721693208fa93353582de452e9
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33367215"
---
# <a name="cdraglistbox-class"></a>Класс CDragListBox
Помимо предоставления функциональных возможностей списка Windows `CDragListBox` класс позволяет пользователю перемещать элементы списка, такие как имена файлов, в окне списка.  
  
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
|[CDragListBox::BeginDrag](#begindrag)|Вызывается платформой, когда начинается операция перетаскивания.|  
|[CDragListBox::CancelDrag](#canceldrag)|Вызывается платформой при отмене операции перетаскивания.|  
|[CDragListBox::Dragging](#dragging)|Вызывается платформой при выполнении операции перетаскивания.|  
|[CDragListBox::DrawInsert](#drawinsert)|Рисует направляющая списка перетаскивания.|  
|[CDragListBox::Dropped](#dropped)|Вызывается структурой после элемент был удален.|  
|[CDragListBox::ItemFromPt](#itemfrompt)|Возвращает координаты перетаскиваемый элемент.|  
  
## <a name="remarks"></a>Примечания  
 Списки с возможностью позволяют упорядочить элементы в списке любым способом, наиболее полезные для них. По умолчанию поле списка будет переместить элемент в новое место в списке. Тем не менее `CDragListBox` объекты могут настраиваться для копирования элементов вместо их перемещения.  
  
 Окно списка связанных с `CDragListBox` класс не должен иметь **LBS_SORT** или **LBS_MULTIPLESELECT** стиля. Описание стили окна список см. в разделе [стили списков](../../mfc/reference/styles-used-by-mfc.md#list-box-styles).  
  
 Чтобы использовать поле со списком перетаскивания в существующем диалоговом окне приложения, добавьте в элемент управления списком шаблон диалогового окна с помощью редактора диалоговых окон, а затем назначьте переменную-член (категории `Control` и тип переменной `CDragListBox`) соответствующее поле списка управлять в шаблон диалогового окна.  
  
 Дополнительные сведения о назначении для переменных-членов элементов управления см. в разделе [ярлык для определения переменных-членов для элементов управления диалоговых окон](../../windows/defining-member-variables-for-dialog-controls.md).  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CListBox](../../mfc/reference/clistbox-class.md)  
  
 `CDragListBox`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxcmn.h  
  
##  <a name="begindrag"></a>  CDragListBox::BeginDrag  
 Вызывается методом framework, когда происходит событие, которое может начать операцию перетаскивания, например нажатие левой кнопки мыши.  
  
```  
virtual BOOL BeginDrag(CPoint pt);
```  
  
### <a name="parameters"></a>Параметры  
 `pt`  
 Объект [CPoint](../../atl-mfc-shared/reference/cpoint-class.md) , содержащий координаты перетаскиваемый элемент.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если перетаскивание разрешен, в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Переопределите эту функцию, если вы хотите контролировать, что происходит, когда начинается операция перетаскивания. Реализация по умолчанию захватывает мышь и остается в режиме перетаскивания, пока пользователь нажимает кнопку мыши влево или вправо или при нажатии клавиши ESC, в какое время отменена операция перетаскивания.  
  
##  <a name="canceldrag"></a>  CDragListBox::CancelDrag  
 Вызывается платформой при отмене операции перетаскивания.  
  
```  
virtual void CancelDrag(CPoint pt);
```  
  
### <a name="parameters"></a>Параметры  
 `pt`  
 Объект [CPoint](../../atl-mfc-shared/reference/cpoint-class.md) , содержащий координаты перетаскиваемый элемент.  
  
### <a name="remarks"></a>Примечания  
 Переопределите эту функцию для обработки специальной обработки для вашего управления "список".  
  
##  <a name="cdraglistbox"></a>  CDragListBox::CDragListBox  
 Создает объект `CDragListBox`.  
  
```  
CDragListBox();
```  
  
##  <a name="dragging"></a>  CDragListBox::Dragging  
 Вызывается платформой при перетаскивании элемента списка в пределах `CDragListBox` объекта.  
  
```  
virtual UINT Dragging(CPoint pt);
```  
  
### <a name="parameters"></a>Параметры  
 `pt`  
 Объект [CPoint](../../atl-mfc-shared/reference/cpoint-class.md) , содержащий x и y экранные координаты курсора.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Идентификатор ресурса для отображения курсора. Возможны следующие значения:  
  
- `DL_COPYCURSOR` Указывает, что элемент не будет скопировано.  
  
- `DL_MOVECURSOR` Указывает, что элемент перемещается.  
  
- `DL_STOPCURSOR` Указывает, что текущего конечного места перетаскивания не является допустимым.  
  
### <a name="remarks"></a>Примечания  
 По умолчанию возвращает `DL_MOVECURSOR`. Переопределите эту функцию, если вы хотите предоставлять дополнительные функциональные возможности.  
  
##  <a name="drawinsert"></a>  CDragListBox::DrawInsert  
 Вызывается платформой для изображения направляющих перед элементом с указанным индексом.  
  
```  
virtual void DrawInsert(int nItem);
```  
  
### <a name="parameters"></a>Параметры  
 `nItem`  
 Отсчитываемый от нуля индекс курсора.  
  
### <a name="remarks"></a>Примечания  
 Значение - 1 очищает направляющая. Переопределите эту функцию для изменения внешнего вида и поведения направляющая.  
  
##  <a name="dropped"></a>  CDragListBox::Dropped  
 Вызывается платформой при удалении элемента в пределах `CDragListBox` объекта.  
  
```  
virtual void Dropped(
    int nSrcIndex,  
    CPoint pt);
```  
  
### <a name="parameters"></a>Параметры  
 *nSrcIndex*  
 Задает отсчитываемый от нуля индекс удаленной строки.  
  
 `pt`  
 Объект [CPoint](../../atl-mfc-shared/reference/cpoint-class.md) , содержащий координаты узла размещения.  
  
### <a name="remarks"></a>Примечания  
 Поведение по умолчанию копирует элемент списка и его данные в новое расположение, а затем удаляет исходный элемент. Переопределите эту функцию для настройки поведения по умолчанию, таких как включение копии элементов списка для переноса в другие местоположения в пределах списка.  
  
##  <a name="itemfrompt"></a>  CDragListBox::ItemFromPt  
 Вызов этой функции для получения отсчитываемый от нуля индекс элемента списка, расположенный `pt`.  
  
```  
int ItemFromPt(
    CPoint pt,  
    BOOL bAutoScroll = TRUE) const;  
```  
  
### <a name="parameters"></a>Параметры  
 `pt`  
 Объект [CPoint](../../atl-mfc-shared/reference/cpoint-class.md) объект, содержащий координаты точки в поле списка.  
  
 *bAutoScroll*  
 Ненулевое значение, если Прокрутка разрешена, в противном случае — 0.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Отсчитываемый от нуля индекс элемента списка перетаскивания.  
  
## <a name="see-also"></a>См. также  
 [Пример MFC TSTCON](../../visual-cpp-samples.md)   
 [CListBox-класс](../../mfc/reference/clistbox-class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Класс CListBox](../../mfc/reference/clistbox-class.md)
