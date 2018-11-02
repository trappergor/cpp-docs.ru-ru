---
title: Класс CMFCRibbonApplicationButton
ms.date: 11/04/2016
f1_keywords:
- CMFCRibbonApplicationButton
- AFXRIBBONBAR/CMFCRibbonApplicationButton
- AFXRIBBONBAR/CMFCRibbonApplicationButton::CMFCRibbonApplicationButton
- AFXRIBBONBAR/CMFCRibbonApplicationButton::SetImage
helpviewer_keywords:
- CMFCRibbonApplicationButton [MFC], CMFCRibbonApplicationButton
- CMFCRibbonApplicationButton [MFC], SetImage
ms.assetid: beb81757-fabd-4641-9130-876ba8505b78
ms.openlocfilehash: 6bf62cc414162a15ee685361cacad8d72fc41b06
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50600357"
---
# <a name="cmfcribbonapplicationbutton-class"></a>Класс CMFCRibbonApplicationButton

Реализует отдельную кнопку, расположенную в левом верхнем углу окна приложения. При нажатии кнопки открывается меню, которое обычно содержит общие команды **Файл** , **Открыть**, **Сохранить**и **Выход**.

## <a name="syntax"></a>Синтаксис

```
class CMFCRibbonApplicationButton : public CMFCRibbonButton
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CMFCRibbonApplicationButton::CMFCRibbonApplicationButton](#cmfcribbonapplicationbutton)|Создает и инициализирует объект `CMFCRibbonApplicationButton`.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|`CMFCRibbonApplicationButton::CreateObject`|Используется платформой для создания динамического экземпляра этого типа класса.|
|`CMFCRibbonApplicationButton::GetThisClass`|Используется инфраструктурой, чтобы получить указатель на [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) объект, связанный с этим типом класса.|
|[CMFCRibbonApplicationButton::SetImage](#setimage)|Назначает изображение кнопка приложения на ленте.|

## <a name="example"></a>Пример

В приведенном ниже примере демонстрируется использование различных методов класса `CMFCRibbonApplicationButton` . В примере показано, как назначить изображение для кнопки приложения и как задать ее всплывающей подсказкой. Этот фрагмент кода входит в состав [примера Draw Client](../../visual-cpp-samples.md).

[!code-cpp[NVC_MFC_DrawClient#4](../../mfc/reference/codesnippet/cpp/cmfcribbonapplicationbutton-class_1.h)]
[!code-cpp[NVC_MFC_DrawClient#5](../../mfc/reference/codesnippet/cpp/cmfcribbonapplicationbutton-class_2.cpp)]

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CMFCRibbonBaseElement](../../mfc/reference/cmfcribbonbaseelement-class.md)

[CMFCRibbonButton](../../mfc/reference/cmfcribbonbutton-class.md)

[CMFCRibbonApplicationButton](../../mfc/reference/cmfcribbonapplicationbutton-class.md)

## <a name="requirements"></a>Требования

**Заголовок:** afxRibbonBar.h

##  <a name="cmfcribbonapplicationbutton"></a>  CMFCRibbonApplicationButton::CMFCRibbonApplicationButton

Создает и инициализирует [CMFCRibbonApplicationButton](../../mfc/reference/cmfcribbonapplicationbutton-class.md) объекта.

```
CMFCRibbonApplicationButton();
CMFCRibbonApplicationButton(UINT uiBmpResID);
  CMFCRibbonApplicationButton(HBITMAP hBmp);
```

### <a name="parameters"></a>Параметры

*uiBmpResID*<br/>
Идентификатор ресурса изображения для отображения кнопки приложения.

*hBmp*<br/>
Дескриптор к растровому изображению, для отображения кнопки приложения.

### <a name="remarks"></a>Примечания

Эта кнопка на ленте приложения имеет отдельную кнопку, расположенную в левом верхнем углу окна приложения. Когда пользователь нажимает эту кнопку, чтобы приложение открывается меню, которое обычно содержит общие **файл** команд, таких как **откройте**, **Сохранить**, и **выхода**.

##  <a name="setimage"></a>  CMFCRibbonApplicationButton::SetImage

Назначает изображения для кнопки приложения.

```
void SetImage(UINT uiBmpResID);
void SetImage(HBITMAP hBmp);
```

### <a name="parameters"></a>Параметры

*uiBmpResID*<br/>
[in] Идентификатор ресурса изображения для отображения кнопки приложения.

*hBmp*<br/>
[in] Дескриптор к растровому изображению, для отображения кнопки приложения.

### <a name="remarks"></a>Примечания

Используйте этот метод, чтобы назначить новый образ в кнопка приложения на ленте после создания кнопки. Кнопка приложения находится в левом верхнем углу окна приложения.

## <a name="see-also"></a>См. также

[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Классы](../../mfc/reference/mfc-classes.md)<br/>
[Класс CMFCRibbonButton](../../mfc/reference/cmfcribbonbutton-class.md)
