---
title: Класс Кмфкпропертигридфилепроперти
ms.date: 11/04/2016
f1_keywords:
- CMFCPropertyGridFileProperty
- AFXPROPERTYGRIDCTRL/CMFCPropertyGridFileProperty
- AFXPROPERTYGRIDCTRL/CMFCPropertyGridFileProperty::CMFCPropertyGridFileProperty
helpviewer_keywords:
- CMFCPropertyGridFileProperty [MFC], CMFCPropertyGridFileProperty
ms.assetid: 2bb8b8b4-47fc-4798-bd5e-dc8ea0b4cd9d
ms.openlocfilehash: 4b64d18a67ea499c202b81481684227200846483
ms.sourcegitcommit: c3bf94210bdb73be80527166264d49e33784152c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/06/2019
ms.locfileid: "68821281"
---
# <a name="cmfcpropertygridfileproperty-class"></a>Класс Кмфкпропертигридфилепроперти

`CMFCPropertyGridFileProperty` Класс поддерживает элемент управления "список свойств", который открывает диалоговое окно выбора файла.

## <a name="syntax"></a>Синтаксис

```
class CMFCPropertyGridFileProperty : public CMFCPropertyGridProperty
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|name|Описание|
|----------|-----------------|
|[CMFCPropertyGridFileProperty::CMFCPropertyGridFileProperty](#cmfcpropertygridfileproperty)|Создает объект `CMFCPropertyGridFileProperty`.|
|`CMFCPropertyGridFileProperty::~CMFCPropertyGridFileProperty`|Деструктор.|

### <a name="public-methods"></a>Открытые методы

|name|Описание|
|----------|-----------------|
|`CMFCPropertyGridFileProperty::GetThisClass`|Используется платформой для получения указателя на объект [крунтимекласс](../../mfc/reference/cruntimeclass-structure.md) , связанный с этим типом класса.|
|`CMFCPropertyGridFileProperty::OnClickButton`|(Переопределяет [кмфкпропертигридпроперти:: онкликкбуттон](../../mfc/reference/cmfcpropertygridproperty-class.md#onclickbutton).)|

### <a name="remarks"></a>Примечания

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[кмфкпропертигридпроперти](../../mfc/reference/cmfcpropertygridproperty-class.md)

[CMFCPropertyGridFileProperty](../../mfc/reference/cmfcpropertygridfileproperty-class.md)

## <a name="requirements"></a>Требования

**Заголовок:** афкспропертигридктрл. h

##  <a name="cmfcpropertygridfileproperty"></a>  CMFCPropertyGridFileProperty::CMFCPropertyGridFileProperty

Создает объект `CMFCPropertyGridFileProperty`.

```
CMFCPropertyGridFileProperty(
    const CString& strName,
    BOOL bOpenFileDialog,
    const CString& strFileName,
    LPCTSTR lpszDefExt=NULL,
    DWORD dwFlags=OFN_HIDEREADONLY|OFN_OVERWRITEPROMPT,
    LPCTSTR lpszFilter=NULL,
    LPCTSTR lpszDescr=NULL,
    DWORD_PTR dwData=0);
```

### <a name="parameters"></a>Параметры

*strName*<br/>
окне Имя свойства.

*бопенфиледиалог*<br/>
окне Значение TRUE, чтобы открыть диалоговое окно **открытия файла** ; Значение FALSE, чтобы открыть диалоговое окно **сохранения файла** .

*strFileName*<br/>
окне Начальное имя файла.

*лпсздефекст*<br/>
окне Строка из одного или нескольких расширений имен файлов. Значение по умолчанию — NULL.

*dwFlags*<br/>
окне Флаги диалогового окна. Значение по умолчанию представляет собой битовую комбинацию (OR) флагов OFN_HIDEREADONLY и OFN_OVERWRITEPROMPT.

*лпсзфилтер*<br/>
окне Строка из одного или нескольких фильтров файлов. Значение по умолчанию — NULL.

*лпсздескр*<br/>
окне Описание элемента свойства. Значение по умолчанию — NULL.

*двдата*<br/>
окне Данные конкретного приложения, связанные с элементом свойства. Например, 32-разрядное целое число или указатель на другие данные. Значение по умолчанию — 0.

### <a name="return-value"></a>Возвращаемое значение

### <a name="remarks"></a>Примечания

Полный список доступных флагов см. в разделе [Структура OpenFileName](/windows/win32/api/commdlg/ns-commdlg-openfilenamew).

### <a name="example"></a>Пример

В этом примере демонстрируется создание объекта с помощью конструктора класса `CMFCPropertyGridFileProperty`. Этот пример является частью демонстрационного [примера Visual Studio](../../overview/visual-cpp-samples.md).

[!code-cpp[NVC_MFC_VisualStudioDemo#22](../../mfc/codesnippet/cpp/cmfcpropertygridfileproperty-class_1.cpp)]

## <a name="see-also"></a>См. также

[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Классы](../../mfc/reference/mfc-classes.md)<br/>
[Класс CMFCPropertyGridCtrl](../../mfc/reference/cmfcpropertygridctrl-class.md)<br/>
[Класс CMFCPropertyGridProperty](../../mfc/reference/cmfcpropertygridproperty-class.md)
