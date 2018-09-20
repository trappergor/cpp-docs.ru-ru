---
title: Фабрики классов и лицензирование | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- vc.mfc.macros.classes
dev_langs:
- C++
helpviewer_keywords:
- class factories [MFC], and licensing
ms.assetid: 53c4856a-4062-46db-9f69-dd4339f746b3
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 5cedcedce14ce2fa6638091f0785f0456dee9891
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46419754"
---
# <a name="class-factories-and-licensing"></a>Фабрики классов и прослушивание

Для создания экземпляра элемента управления OLE, приложения-контейнера вызывает функцию-член фабрики класса элемента управления. Так как элемент управления — это фактический объект OLE, фабрика классов отвечает за создание экземпляров элемента управления. Каждый класс элемента управления OLE, должен иметь фабрики класса.

Другой важной особенностью элементов управления OLE является способностью принудительно лицензию. Автоматически позволяет внедрять лицензирования во время создания проекта элемента управления. Дополнительные сведения о лицензировании управления см. в статье [элементы управления ActiveX: Лицензирование элемента управления ActiveX](../../mfc/mfc-activex-controls-licensing-an-activex-control.md).

В следующей таблице перечислены несколько макросы и функции, которые используются для объявления и реализации фабрики класса элемента управления и лицензии элемента управления.

### <a name="class-factories-and-licensing"></a>Фабрики классов и прослушивание

|||
|-|-|
|[DECLARE_OLECREATE_EX](#declare_olecreate_ex)|Объявляет фабрика класса для страницы элемента управления или свойства OLE.|
|[IMPLEMENT_OLECREATE_EX](#implement_olecreate_ex)|Реализует элемент управления `GetClassID` функции и объявляет экземпляр фабрики класса.|
|[BEGIN_OLEFACTORY](#begin_olefactory)|Начинает объявление любого лицензирования функций.|
|[END_OLEFACTORY](#end_olefactory)|Завершает объявление любого лицензирования функций.|
|[AfxVerifyLicFile](#afxverifylicfile)|Проверяет, является ли элемент управления лицензируется для использования на определенном компьютере.|

##  <a name="declare_olecreate_ex"></a>  DECLARE_OLECREATE_EX

Объявляет фабрику класса и `GetClassID` функция-член класса элемента управления.

```
DECLARE_OLECREATE_EX(class_name)
```

### <a name="parameters"></a>Параметры

*class_name*<br/>
Имя класса элемента управления.

### <a name="remarks"></a>Примечания

Используйте этот макрос в файле заголовка класса элемента управления для элемента управления, не поддерживает лицензирование.

Обратите внимание на то, что этот макрос выполняет те же функции, как в следующем примере кода:

[!code-cpp[NVC_MFCAxCtl#14](../../mfc/reference/codesnippet/cpp/class-factories-and-licensing_1.h)]

### <a name="requirements"></a>Требования

  **Заголовок** afxctl.h

##  <a name="implement_olecreate_ex"></a>  IMPLEMENT_OLECREATE_EX

Реализует фабрику класса элемента управления и [GetClassID](../../mfc/reference/colecontrol-class.md#getclassid) функция-член класса элемента управления.

```
IMPLEMENT_OLECREATE_EX(
   class_name,
    external_name,
    l,
    w1,
    w2,
    b1,
    b2,
    b3,
    b4,
    b5,
    b6,
    b7,
    b8)
```

### <a name="parameters"></a>Параметры

*class_name*<br/>
Имя класса страницы свойств элемента управления.

*параметр external_name*<br/>
Имя объекта, для приложений.

*l, w1, w2, b1, В2, b3, b4, b5, b6, b7, b8*<br/>
Компоненты класса CLSID. Дополнительные сведения об этих параметрах см. в примечаниях к описанию [IMPLEMENT_OLECREATE](run-time-object-model-services.md#implement_olecreate).

### <a name="remarks"></a>Примечания

Этот макрос должен указываться в файле реализации для любого класса элемента управления, который использует declare_olecreate_ex-макрос или BEGIN_OLEFACTORY и END_OLEFACTORY макросы. Внешнее имя является идентификатором элемента управления OLE, который предоставляется для других приложений. Контейнеры используют это имя для запроса объекта данного класса элемента управления.

### <a name="requirements"></a>Требования

  **Заголовок** afxctl.h

##  <a name="begin_olefactory"></a>  BEGIN_OLEFACTORY

Начинает объявление класса фабрики в файле заголовка класса элемента управления.

```
BEGIN_OLEFACTORY(class_name)
```

### <a name="parameters"></a>Параметры

*class_name*<br/>
Задает имя класса элемента управления, фабрики класса, это.

### <a name="remarks"></a>Примечания

Объявления класса фабрики лицензирования функции следует начинать сразу после BEGIN_OLEFACTORY.

### <a name="requirements"></a>Требования

  **Заголовок** afxctl.h

##  <a name="end_olefactory"></a>  END_OLEFACTORY

Завершает объявление фабрики класса элемента управления.

```
END_OLEFACTORY(class_name)
```

### <a name="parameters"></a>Параметры

*class_name*<br/>
Имя класса элемента управления, фабрики класса, это.

### <a name="requirements"></a>Требования

  **Заголовок** afxctl.h

##  <a name="afxverifylicfile"></a>  AfxVerifyLicFile

Вызывайте эту функцию, чтобы убедиться, что файл лицензии с именем `pszLicFileName` является допустимым для элемента управления OLE.

```
BOOL AFXAPI AfxVerifyLicFile(
    HINSTANCE  hInstance,
    LPCTSTR  pszLicFileName,
    LPOLESTR  pszLicFileContents,
    UINT cch = -1);
```

### <a name="parameters"></a>Параметры

*hInstance*<br/>
Дескриптор экземпляра библиотеки DLL, связанные с лицензированный элемент управления.

*pszLicFileName*<br/>
Указывает строку символов с завершающим нулем, содержащую имя файла лицензии.

*pszLicFileContents*<br/>
Указывает последовательность байтов, которое должно соответствовать последовательности, найден в начале файла лицензии.

*cch*<br/>
Число символов в *pszLicFileContents*.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если существует файл лицензии и начинается с последовательности символов в *pszLicFileContents*; в противном случае — 0.

### <a name="remarks"></a>Примечания

Если *cch* равно -1, эта функция использует:

[!code-cpp[NVC_MFC_Utilities#36](../../mfc/codesnippet/cpp/class-factories-and-licensing_2.cpp)]

### <a name="requirements"></a>Требования

  **Заголовок** afxctl.h

## <a name="see-also"></a>См. также

[Макросы и глобальные объекты](../../mfc/reference/mfc-macros-and-globals.md)
