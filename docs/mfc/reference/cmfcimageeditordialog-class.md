---
title: "Класс CMFCImageEditorDialog | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMFCImageEditorDialog
dev_langs:
- C++
helpviewer_keywords:
- CMFCImageEditorDialog class
ms.assetid: 6a7d08f3-1ec2-4062-9b79-a0c2776b58d1
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
translationtype: Machine Translation
ms.sourcegitcommit: 040985df34f2613b4e4fae29498721aef15d50cb
ms.openlocfilehash: 1a629f9699aa2d6fb185737b51b36259ce574fe0
ms.lasthandoff: 02/24/2017

---
# <a name="cmfcimageeditordialog-class"></a>Класс CMFCImageEditorDialog
`CMFCImageEditorDialog` Класс поддерживает диалоговое окно редактора изображений.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CMFCImageEditorDialog : public CDialogEx  
```  
  
## <a name="members"></a>Члены  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CMFCImageEditorDialog::CMFCImageEditorDialog](#cmfcimageeditordialog)|Создает объект `CMFCImageEditorDialog`.|  
  
## <a name="remarks"></a>Примечания  
 `CMFCImageEditorDialog` Класс предоставляет диалоговое окно, которое включает в себя:  
  
-   Область изображения, которая используется для изменения отдельных пикселов в изображении.  
  
-   Графические средства для изменения пикселов в области рисунка.  
  
-   Цветовая палитра, чтобы указать цвет, используемый для рисования.  
  
-   В области предварительного просмотра, которое отображает эффект от изменения.  
  
 Ниже показано диалоговое окно редактора изображений.  
  
 ![Диалоговое окно cmfcimageeditordialog](../../mfc/reference/media/imageedit.png "imageedit")  
  
 Один из способов использования `CMFCImageEditorDialog` объекта является его передача `CBitmap` изображение для редактирования. Нельзя создать большое изображение, поскольку область редактирования изображения имеет ограниченный размер и размер логический пиксел регулируется по ее размерам. Вызов `DoModal` метод для запуска модального диалогового окна.  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CDialog](../../mfc/reference/cdialog-class.md)  
  
 [CDialogEx](../../mfc/reference/cdialogex-class.md)  
  
 [CMFCImageEditorDialog](../../mfc/reference/cmfcimageeditordialog-class.md)  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afximageeditordialog.h  
  
##  <a name="a-namecmfcimageeditordialoga--cmfcimageeditordialogcmfcimageeditordialog"></a><a name="cmfcimageeditordialog"></a>CMFCImageEditorDialog::CMFCImageEditorDialog  
 Создает объект `CMFCImageEditorDialog`.  
  
```  
CMFCImageEditorDialog(
    CBitmap* pBitmap,  
    CWnd* pParent=NULL,  
    int nBitsPixel=-1);
```  
  
### <a name="parameters"></a>Параметры  
 `pBitmap`  
 Указатель на изображение.  
  
 `pParent`  
 Указатель на родительское окно текущего диалогового редактора изображений.  
  
 `nBitsPixel`  
 Количество битов, используемых для представления цвета одной точки, которая также называется глубиной цвета.  Если `nBitsPixel` параметр равен -1, глубиной цвета является производным от изображение, указанное в `pBitmap` параметр. Значение по умолчанию — -1.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Чтобы изменить изображения, передать указатель на изображение для `CMFCImageEditorDialog` конструктор. Затем вызовите `DoModal` метод для открытия модального диалогового окна. Когда `DoModal` метод возвращает растровое изображение содержит новый образ.  
  
### <a name="remarks"></a>Примечания  
  
### <a name="example"></a>Пример  
 Следующий пример демонстрирует создания объекта `CMFCImageEditorDialog` класса. Этот пример является частью [пример создания новых элементов управления](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_NewControls №&8;](../../mfc/reference/codesnippet/cpp/cmfcimageeditordialog-class_1.cpp)]  
[!code-cpp[NVC_MFC_NewControls&#40;](../../mfc/reference/codesnippet/cpp/cmfcimageeditordialog-class_2.cpp)]  
  
## <a name="see-also"></a>См. также  
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Классы](../../mfc/reference/mfc-classes.md)   
 [Класс CMFCToolBar](../../mfc/reference/cmfctoolbar-class.md)

