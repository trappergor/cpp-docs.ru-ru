---
title: Класс CMFCRibbonUndoButton | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CMFCRibbonUndoButton
- AFXRIBBONUNDOBUTTON/CMFCRibbonUndoButton
- AFXRIBBONUNDOBUTTON/CMFCRibbonUndoButton::CMFCRibbonUndoButton
- AFXRIBBONUNDOBUTTON/CMFCRibbonUndoButton::AddUndoAction
- AFXRIBBONUNDOBUTTON/CMFCRibbonUndoButton::CleanUpUndoList
- AFXRIBBONUNDOBUTTON/CMFCRibbonUndoButton::GetActionNumber
- AFXRIBBONUNDOBUTTON/CMFCRibbonUndoButton::HasMenu
dev_langs:
- C++
helpviewer_keywords:
- CMFCRibbonUndoButton [MFC], CMFCRibbonUndoButton
- CMFCRibbonUndoButton [MFC], AddUndoAction
- CMFCRibbonUndoButton [MFC], CleanUpUndoList
- CMFCRibbonUndoButton [MFC], GetActionNumber
- CMFCRibbonUndoButton [MFC], HasMenu
ms.assetid: 5c42adf7-871d-4239-901e-47ae7fb816fc
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 11c83332c12daa6753add0618367b90f8c759532
ms.sourcegitcommit: 26fff80635bd1d51bc51899203fddfea8b29b530
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/05/2018
ms.locfileid: "37848772"
---
# <a name="cmfcribbonundobutton-class"></a>Класс CMFCRibbonUndoButton
`CMFCRibbonUndoButton` Класс реализует кнопку раскрывающегося списка, содержащего последние команды пользователя. Пользователи могут выбрать один или несколько последних команд из раскрывающегося списка, чтобы повторить или отменить их.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CMFCRibbonUndoButton : public CMFCRibbonGallery  
```  
  
## <a name="members"></a>Участники  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CMFCRibbonUndoButton::CMFCRibbonUndoButton](#cmfcribbonundobutton)|Создает новый `CMFCRibbonUndoButton` объекта, используя идентификатор команды, указанной вами, текстовую метку и изображений из списка изображений родительского объекта.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CMFCRibbonUndoButton::AddUndoAction](#addundoaction)|Добавляет новое действие в список действий.|  
|[CMFCRibbonUndoButton::CleanUpUndoList](#cleanupundolist)|Очищает список действий, представляющий стрелку раскрывающегося списка.|  
|[CMFCRibbonUndoButton::GetActionNumber](#getactionnumber)|Определяет количество элементов, которые пользователь выбрал в раскрывающемся списке.|  
|[CMFCRibbonUndoButton::HasMenu](#hasmenu)|Указывает, содержит ли объект меню.|  
  
## <a name="remarks"></a>Примечания  
 `CMFCRibbonUndoButton` Класс использует стек для представления раскрывающегося списка.  
  
## <a name="example"></a>Пример  
 Следующий пример демонстрирует создание объекта класса `CMFCRibbonUndoButton` класса и добавьте новое действие в список действий. Этот фрагмент кода является частью [пример мини-приложения ленты](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_RibbonGadgets#2](../../mfc/reference/codesnippet/cpp/cmfcribbonundobutton-class_1.cpp)]  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CMFCRibbonBaseElement](../../mfc/reference/cmfcribbonbaseelement-class.md)  
  
 [CMFCRibbonButton](../../mfc/reference/cmfcribbonbutton-class.md)  
  
 [CMFCRibbonGallery](../../mfc/reference/cmfcribbongallery-class.md)  
  
 [CMFCRibbonUndoButton](../../mfc/reference/cmfcribbonundobutton-class.md)  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxribbonundobutton.h  
  
##  <a name="addundoaction"></a>  CMFCRibbonUndoButton::AddUndoAction  
 Добавляет новое действие в список действий.  
  
```  
void AddUndoAction(LPCTSTR lpszLabel);
```  
  
### <a name="parameters"></a>Параметры  
 [in] *lpszLabel*  
 Метка действия, которое будет отображаться в раскрывающемся списке.  
  
##  <a name="cleanupundolist"></a>  CMFCRibbonUndoButton::CleanUpUndoList  
 Очищает список действий, представляющий стрелку раскрывающегося списка.  
  
```  
void CleanUpUndoList();
```  
  
##  <a name="cmfcribbonundobutton"></a>  CMFCRibbonUndoButton::CMFCRibbonUndoButton  
 Создает новый `CMFCRibbonUndoButton` объекта, используя идентификатор команды, указанной вами, текстовую метку и изображений из списка изображений родительского объекта.  
  
```  
CMFCRibbonUndoButton(
    UINT nID,  
    LPCTSTR lpszText,  
    int nSmallImageIndex=-1,  
    int nLargeImageIndex=-1);

 
CMFCRibbonUndoButton(
    UINT nID,  
    LPCTSTR lpszText,  
    HICON hIcon);
```  
  
### <a name="parameters"></a>Параметры  
 [in] *nID*  
 Указывает идентификатор команды.  
  
 [in] *lpszText*  
 Задает текстовую подпись кнопки.  
  
 [in] *nSmallImageIndex*  
 Отсчитываемый от нуля индекс в списке изображений родительского объекта для небольшое изображение кнопки.  
  
 [in] *nLargeImageIndex*  
 Отсчитываемый от нуля индекс в списке изображений родительского объекта для большого изображения кнопки.  
  
 [in] *hIcon*  
 Дескриптор значка, который можно использовать в качестве изображения кнопки.  
  
##  <a name="getactionnumber"></a>  CMFCRibbonUndoButton::GetActionNumber  
 Определяет количество элементов, которые пользователь выбрал в раскрывающемся списке.  
  
```  
int GetActionNumber() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Число элементов, которые пользователь выбрал.  
  
##  <a name="hasmenu"></a>  CMFCRibbonUndoButton::HasMenu  
 Указывает, содержит ли объект меню.  
  
```  
virtual BOOL HasMenu() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Всегда возвращает значение TRUE.  
  
### <a name="remarks"></a>Примечания  
  
## <a name="see-also"></a>См. также  
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Классы](../../mfc/reference/mfc-classes.md)   
 [Класс CMFCRibbonGallery](../../mfc/reference/cmfcribbongallery-class.md)   
 [Класс CMFCRibbonButton](../../mfc/reference/cmfcribbonbutton-class.md)
