---
title: Класс CMFCImageEditorDialog
ms.date: 11/19/2018
f1_keywords:
- CMFCImageEditorDialog
- AFXIMAGEEDITORDIALOG/CMFCImageEditorDialog
- AFXIMAGEEDITORDIALOG/CMFCImageEditorDialog::CMFCImageEditorDialog
helpviewer_keywords:
- CMFCImageEditorDialog [MFC], CMFCImageEditorDialog
ms.assetid: 6a7d08f3-1ec2-4062-9b79-a0c2776b58d1
ms.openlocfilehash: 57b1df49616967841a433a36a504beed0b900cde
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/04/2019
ms.locfileid: "57278539"
---
# <a name="cmfcimageeditordialog-class"></a>Класс CMFCImageEditorDialog

`CMFCImageEditorDialog` Класс поддерживает в диалоговом окне редактора изображений.

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

- Область картинки, можно использовать для изменения отдельных пикселей изображения.

- Графические средства для изменения пиксели в области рисунка.

- Цветовая палитра, чтобы указать цвет, используемый для рисования.

- В области предварительного просмотра, который отображает эффект от изменения.

Ниже показан редактор изображений диалоговое окно.

![Диалоговое окно CMFCImageEditorDialog](../../mfc/reference/media/imageedit.png "диалоговое окно CMFCImageEditorDialog")

Один из способов использования `CMFCImageEditorDialog` объекта является его передача `CBitmap` изображение для редактирования. Не создавайте большое изображение, так как область редактирования изображения имеет ограниченный размер и размер в логических пикселях корректируется по ее размерам. Вызовите `DoModal` метод, чтобы запустить модальное диалоговое окно.

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

*pBitmap*<br/>
Указатель на изображение.

*pParent*<br/>
Указатель на родительское окно текущего диалогового редактора изображений.

*nBitsPixel*<br/>
Количество битов, используемых для представления цвета одного пикселя, который также называется глубиной цвета.  Если *nBitsPixel* параметра равно -1, глубина цвета является производным от изображение, указанное *pBitmap* параметра. Значение по умолчанию — -1.

### <a name="return-value"></a>Возвращаемое значение

Чтобы изменить изображение, передать указатель образа `CMFCImageEditorDialog` конструктор. Затем вызовите `DoModal` метод, чтобы открыть модальное диалоговое окно. Когда `DoModal` возвращает метод, битовая карта содержит новый образ.

### <a name="remarks"></a>Примечания

### <a name="example"></a>Пример

Следующий пример демонстрирует создание объекта класса `CMFCImageEditorDialog` класса. Этот пример является частью [пример новых элементов управления](../../visual-cpp-samples.md).

[!code-cpp[NVC_MFC_NewControls#8](../../mfc/reference/codesnippet/cpp/cmfcimageeditordialog-class_1.cpp)]
[!code-cpp[NVC_MFC_NewControls#40](../../mfc/reference/codesnippet/cpp/cmfcimageeditordialog-class_2.cpp)]

## <a name="see-also"></a>См. также

[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Классы](../../mfc/reference/mfc-classes.md)<br/>
[Класс CMFCToolBar](../../mfc/reference/cmfctoolbar-class.md)
