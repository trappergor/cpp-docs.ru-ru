---
title: Класс CMFCPropertyGridFileProperty
ms.date: 11/04/2016
f1_keywords:
- CMFCPropertyGridFileProperty
- AFXPROPERTYGRIDCTRL/CMFCPropertyGridFileProperty
- AFXPROPERTYGRIDCTRL/CMFCPropertyGridFileProperty::CMFCPropertyGridFileProperty
helpviewer_keywords:
- CMFCPropertyGridFileProperty [MFC], CMFCPropertyGridFileProperty
ms.assetid: 2bb8b8b4-47fc-4798-bd5e-dc8ea0b4cd9d
ms.openlocfilehash: 20a0a50198357602d70a2111c6884058f7578af7
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "58773337"
---
# <a name="cmfcpropertygridfileproperty-class"></a>Класс CMFCPropertyGridFileProperty

`CMFCPropertyGridFileProperty` Класс поддерживает элемент управления списка свойств, которая открывает диалоговое окно выбора файла.

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
|`CMFCPropertyGridFileProperty::GetThisClass`|Используется инфраструктурой, чтобы получить указатель на [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) объект, связанный с этим типом класса.|
|`CMFCPropertyGridFileProperty::OnClickButton`|(Переопределяет [CMFCPropertyGridProperty::OnClickButton](../../mfc/reference/cmfcpropertygridproperty-class.md#onclickbutton).)|

### <a name="remarks"></a>Примечания

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CMFCPropertyGridProperty](../../mfc/reference/cmfcpropertygridproperty-class.md)

[CMFCPropertyGridFileProperty](../../mfc/reference/cmfcpropertygridfileproperty-class.md)

## <a name="requirements"></a>Требования

**Заголовок:** afxpropertygridctrl.h

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
[in] Имя свойства.

*bOpenFileDialog*<br/>
[in] Значение true, чтобы открыть **открыть файл** диалоговом окне; Значение FALSE, чтобы открыть **сохранить файл** диалоговое окно.

*strFileName*<br/>
[in] Исходное имя файла.

*lpszDefExt*<br/>
[in] Строка, содержащая одно или несколько расширений имени файла. Значение по умолчанию имеет значение NULL.

*dwFlags*<br/>
[in] Флаги диалогового окна. Значение по умолчанию представляет собой битовую комбинацию (OR) флагов OFN_HIDEREADONLY и OFN_OVERWRITEPROMPT.

*lpszFilter*<br/>
[in] Строка, содержащая один или несколько фильтров файлов. Значение по умолчанию имеет значение NULL.

*lpszDescr*<br/>
[in] Описание элемента свойства. Значение по умолчанию имеет значение NULL.

*dwData*<br/>
[in] Данные конкретного приложения, связанный с этим элементом свойства. Например, 32-разрядное целое число или указатель на другие данные. Значение по умолчанию — 0.

### <a name="return-value"></a>Возвращаемое значение

### <a name="remarks"></a>Примечания

Полный список доступных флагов см. в разделе [структуры OPENFILENAME](/windows/desktop/api/commdlg/ns-commdlg-tagofna).

### <a name="example"></a>Пример

В этом примере демонстрируется создание объекта с помощью конструктора класса `CMFCPropertyGridFileProperty`. Этот пример является частью [Visual Studio демонстрационного](../../overview/visual-cpp-samples.md).

[!code-cpp[NVC_MFC_VisualStudioDemo#22](../../mfc/codesnippet/cpp/cmfcpropertygridfileproperty-class_1.cpp)]

## <a name="see-also"></a>См. также

[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Классы](../../mfc/reference/mfc-classes.md)<br/>
[Класс CMFCPropertyGridCtrl](../../mfc/reference/cmfcpropertygridctrl-class.md)<br/>
[Класс CMFCPropertyGridProperty](../../mfc/reference/cmfcpropertygridproperty-class.md)
