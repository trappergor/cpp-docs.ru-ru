---
title: Класс CMFCImageEditorDialog | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CMFCImageEditorDialog
- AFXIMAGEEDITORDIALOG/CMFCImageEditorDialog
- AFXIMAGEEDITORDIALOG/CMFCImageEditorDialog::CMFCImageEditorDialog
dev_langs:
- C++
helpviewer_keywords:
- CMFCImageEditorDialog [MFC], CMFCImageEditorDialog
ms.assetid: 6a7d08f3-1ec2-4062-9b79-a0c2776b58d1
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 795e5548e93323af389c3faeaefa7dda0bf7d80c
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33376253"
---
# <a name="cmfcimageeditordialog-class"></a>Класс CMFCImageEditorDialog
`CMFCImageEditorDialog` Класс поддерживает диалоговое окно редактора изображений.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CMFCImageEditorDialog : public CDialogEx  
```  
  
## <a name="members"></a>Участники  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CMFCImageEditorDialog::CMFCImageEditorDialog](#cmfcimageeditordialog)|Создает объект `CMFCImageEditorDialog`.|  
  
## <a name="remarks"></a>Примечания  
 `CMFCImageEditorDialog` Класс предоставляет диалоговое окно, включает в себя:  
  
-   Область картинки, использовать для изменения отдельных пикселов в изображении.  
  
-   Графические средства для изменения пикселов в области рисунка.  
  
-   Цветовая палитра, чтобы указать цвет, используемый для рисования.  
  
-   В области предварительного просмотра, которое отображает эффект от изменения.  
  
 На следующем рисунке редактора изображений диалоговое окно.  
  
 ![Диалоговое окно cmfcimageeditordialog](../../mfc/reference/media/imageedit.png "imageedit")  
  
 Один из способов использования `CMFCImageEditorDialog` объекта является его передача `CBitmap` образ, который нужно изменить. Не создавайте большое изображение, из-за изменения области изображения имеет ограниченный размер и размер логического пикселей изменяется по ее размерам. Вызовите `DoModal` метода для запуска модального диалогового окна.  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CDialog](../../mfc/reference/cdialog-class.md)  
  
 [CDialogEx](../../mfc/reference/cdialogex-class.md)  
  
 [CMFCImageEditorDialog](../../mfc/reference/cmfcimageeditordialog-class.md)  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afximageeditordialog.h  
  
##  <a name="cmfcimageeditordialog"></a>  CMFCImageEditorDialog::CMFCImageEditorDialog  
 Создает объект `CMFCImageEditorDialog`.  
  
```  
CMFCImageEditorDialog(
    CBitmap* pBitmap,  
    CWnd* pParent=NULL,  
    int nBitsPixel=-1);
```  
  
### <a name="parameters"></a>Параметры  
 `pBitmap`  
 Указатель на изображения.  
  
 `pParent`  
 Указатель на родительское окно текущего диалогового редактора изображений.  
  
 `nBitsPixel`  
 Количество битов, используемых для представления цвета одной точки, которую также называют глубину цвета.  Если `nBitsPixel` параметра равно -1, глубину цвета является производным от изображение, указанное свойством `pBitmap` параметра. Значение по умолчанию — -1.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Чтобы изменить изображение, передать указатель на изображения для `CMFCImageEditorDialog` конструктор. Затем вызовите `DoModal` метод для открытия модального диалогового окна. Когда `DoModal` метод возвращает растровое изображение содержит новый образ.  
  
### <a name="remarks"></a>Примечания  
  
### <a name="example"></a>Пример  
 Следующий пример демонстрирует создание объекта `CMFCImageEditorDialog` класса. Данный пример является частью [образец новые элементы управления](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_NewControls#8](../../mfc/reference/codesnippet/cpp/cmfcimageeditordialog-class_1.cpp)]  
[!code-cpp[NVC_MFC_NewControls#40](../../mfc/reference/codesnippet/cpp/cmfcimageeditordialog-class_2.cpp)]  
  
## <a name="see-also"></a>См. также  
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Классы](../../mfc/reference/mfc-classes.md)   
 [Класс CMFCToolBar](../../mfc/reference/cmfctoolbar-class.md)
