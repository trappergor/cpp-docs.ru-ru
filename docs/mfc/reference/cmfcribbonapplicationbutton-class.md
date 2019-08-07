---
title: Класс Кмфкриббонаппликатионбуттон
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
ms.openlocfilehash: d1dc8ef6e801623aa96cb4b47936413cd17f24f0
ms.sourcegitcommit: c3bf94210bdb73be80527166264d49e33784152c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/06/2019
ms.locfileid: "68821241"
---
# <a name="cmfcribbonapplicationbutton-class"></a>Класс Кмфкриббонаппликатионбуттон

Реализует отдельную кнопку, расположенную в левом верхнем углу окна приложения. При нажатии кнопки открывается меню, которое обычно содержит общие команды **Файл** , **Открыть**, **Сохранить**и **Выход**.

## <a name="syntax"></a>Синтаксис

```
class CMFCRibbonApplicationButton : public CMFCRibbonButton
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|name|Описание|
|----------|-----------------|
|[Кмфкриббонаппликатионбуттон:: Кмфкриббонаппликатионбуттон](#cmfcribbonapplicationbutton)|Создает и инициализирует объект `CMFCRibbonApplicationButton`.|

### <a name="public-methods"></a>Открытые методы

|name|Описание|
|----------|-----------------|
|`CMFCRibbonApplicationButton::CreateObject`|Используется платформой для создания динамического экземпляра этого типа класса.|
|`CMFCRibbonApplicationButton::GetThisClass`|Используется платформой для получения указателя на объект [крунтимекласс](../../mfc/reference/cruntimeclass-structure.md) , связанный с этим типом класса.|
|[Кмфкриббонаппликатионбуттон:: Сетимаже](#setimage)|Назначает изображение для кнопки приложения на ленте.|

## <a name="example"></a>Пример

В приведенном ниже примере демонстрируется использование различных методов класса `CMFCRibbonApplicationButton` . В примере показано, как назначить изображение кнопке приложения и как задать его подсказку. Этот фрагмент кода входит в состав [примера Draw Client](../../overview/visual-cpp-samples.md).

[!code-cpp[NVC_MFC_DrawClient#4](../../mfc/reference/codesnippet/cpp/cmfcribbonapplicationbutton-class_1.h)]
[!code-cpp[NVC_MFC_DrawClient#5](../../mfc/reference/codesnippet/cpp/cmfcribbonapplicationbutton-class_2.cpp)]

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CMFCRibbonBaseElement](../../mfc/reference/cmfcribbonbaseelement-class.md)

[CMFCRibbonButton](../../mfc/reference/cmfcribbonbutton-class.md)

[кмфкриббонаппликатионбуттон](../../mfc/reference/cmfcribbonapplicationbutton-class.md)

## <a name="requirements"></a>Требования

**Заголовок:** афксриббонбар. h

##  <a name="cmfcribbonapplicationbutton"></a>Кмфкриббонаппликатионбуттон:: Кмфкриббонаппликатионбуттон

Создает и инициализирует объект [кмфкриббонаппликатионбуттон](../../mfc/reference/cmfcribbonapplicationbutton-class.md) .

```
CMFCRibbonApplicationButton();
CMFCRibbonApplicationButton(UINT uiBmpResID);
CMFCRibbonApplicationButton(HBITMAP hBmp);
```

### <a name="parameters"></a>Параметры

*уибмпресид*<br/>
Идентификатор ресурса изображения, отображаемого на кнопке приложения.

*хбмп*<br/>
Маркер для растрового изображения, отображаемого на кнопке приложения.

### <a name="remarks"></a>Примечания

Кнопка «приложение-лента» — это специальная кнопка, расположенная в левом верхнем углу окна приложения. Когда пользователь нажимает эту кнопку, приложение открывает меню, которое обычно содержит общие команды **File** , такие как **Открытие**, **Сохранение**и **выход**.

##  <a name="setimage"></a>Кмфкриббонаппликатионбуттон:: Сетимаже

Назначает изображение кнопке приложения.

```
void SetImage(UINT uiBmpResID);
void SetImage(HBITMAP hBmp);
```

### <a name="parameters"></a>Параметры

*уибмпресид*<br/>
окне Идентификатор ресурса изображения, отображаемого на кнопке приложения.

*хбмп*<br/>
окне Маркер для растрового изображения, отображаемого на кнопке приложения.

### <a name="remarks"></a>Примечания

Используйте этот метод для назначения нового изображения кнопке приложения-ленты после создания кнопки. Кнопка приложения находится в левом верхнем углу окна приложения.

## <a name="see-also"></a>См. также

[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Классы](../../mfc/reference/mfc-classes.md)<br/>
[Класс CMFCRibbonButton](../../mfc/reference/cmfcribbonbutton-class.md)
