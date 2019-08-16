---
title: Класс Кмфктулбаркомбобокседит
ms.date: 11/04/2016
f1_keywords:
- CMFCToolBarComboBoxEdit
- AFXTOOLBARCOMBOBOXBUTTON/CMFCToolBarComboBoxEdit
- AFXTOOLBARCOMBOBOXBUTTON/CMFCToolBarComboBoxEdit::CMFCToolBarComboBoxEdit
helpviewer_keywords:
- CMFCToolBarComboBoxEdit [MFC], CMFCToolBarComboBoxEdit
ms.assetid: 4789c34a-ce58-48ba-a26f-38748b601352
ms.openlocfilehash: 2a0ab1766f42d34c86339cffb86f876358c97a4a
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/15/2019
ms.locfileid: "69504870"
---
# <a name="cmfctoolbarcomboboxedit-class"></a>Класс Кмфктулбаркомбобокседит

Платформа использует `CMFCToolBarComboBoxEdit` класс для создания кнопки на панели инструментов, которая ведет себя как редактируемый элемент управления "поле со списком".

## <a name="syntax"></a>Синтаксис

```
class CMFCToolBarComboBoxEdit : public CEdit
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|name|Описание|
|----------|-----------------|
|[Кмфктулбаркомбобокседит:: Кмфктулбаркомбобокседит](#cmfctoolbarcomboboxedit)|Создает объект `CMFCToolBarComboBoxEdit`.|
|`CMFCToolBarComboBoxEdit::~CMFCToolBarComboBoxEdit`|Деструктор.|

### <a name="public-methods"></a>Открытые методы

|name|Описание|
|----------|-----------------|
|`CMFCToolBarComboBoxEdit::PreTranslateMessage`|Преобразует сообщения окна до их отправки в функции Windows [TranslateMessage](/windows/win32/api/winuser/nf-winuser-translatemessage) и [DispatchMessage](/windows/win32/api/winuser/nf-winuser-dispatchmessage) . (Переопределяет [CWnd::PreTranslateMessage](../../mfc/reference/cwnd-class.md#pretranslatemessage).)|

### <a name="remarks"></a>Примечания

Создайте класс, производный от `CMFCToolBarComboBoxEdit` класса, для настройки его операций изменения.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CEdit](../../mfc/reference/cedit-class.md)

[кмфктулбаркомбобокседит](../../mfc/reference/cmfctoolbarcomboboxedit-class.md)

## <a name="requirements"></a>Требования

**Заголовок:** афкстулбаркомбобоксбуттон. h

##  <a name="cmfctoolbarcomboboxedit"></a>Кмфктулбаркомбобокседит:: Кмфктулбаркомбобокседит

Создает объект `CMFCToolBarComboBoxEdit`.

```
CMFCToolBarComboBoxEdit(CMFCToolBarComboBoxButton& combo);
```

### <a name="parameters"></a>Параметры

*поле*<br/>
окне Ссылка на объект [кмфктулбаркомбобоксбуттон](../../mfc/reference/cmfctoolbarcomboboxbutton-class.md) , который является кнопкой панели инструментов, содержащей элемент управления "поле со списком".

### <a name="example"></a>Пример

В следующем примере показано, как создать объект `CMFCToolBarComboBoxEdit` класса. Этот фрагмент кода является частью [примера демонстрационной версии IE](../../overview/visual-cpp-samples.md).

[!code-cpp[NVC_MFC_IEDemo#5](../../mfc/reference/codesnippet/cpp/cmfctoolbarcomboboxedit-class_1.cpp)]

## <a name="see-also"></a>См. также

[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Классы](../../mfc/reference/mfc-classes.md)<br/>
[Класс CMFCToolBarComboBoxButton](../../mfc/reference/cmfctoolbarcomboboxbutton-class.md)
