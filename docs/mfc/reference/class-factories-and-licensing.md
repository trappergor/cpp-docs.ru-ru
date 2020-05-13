---
title: Фабрики классов и прослушивание
ms.date: 11/04/2016
helpviewer_keywords:
- class factories [MFC], and licensing
ms.assetid: 53c4856a-4062-46db-9f69-dd4339f746b3
ms.openlocfilehash: e3fed6520cdbe0fd964e4e80e7c9ed9b78296d16
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81372309"
---
# <a name="class-factories-and-licensing"></a>Фабрики классов и прослушивание

Чтобы создать экземпляр управления OLE, контейнерное приложение вызывает функцию члена фабрики класса управления. Поскольку ваш элемент управления является фактическим объектом OLE, фабрика класса отвечает за создание экземпляров вашего управления. Каждый класс управления OLE должен иметь классовую фабрику.

Еще одной важной особенностью элементов управления OLE является их способность применять лицензию. ControlWizard позволяет включать лицензирование во время создания вашего проекта управления. Для получения дополнительной информации о [ActiveX Controls: Licensing An ActiveX Control](../../mfc/mfc-activex-controls-licensing-an-activex-control.md)лицензировании управления см.

В следующей таблице перечислены несколько макросов и функций, используемых для декларировать и реализовывать фабрику классов вашего управления и лицензировать ваш контроль.

### <a name="class-factories-and-licensing"></a>Фабрики классов и прослушивание

|||
|-|-|
|[DECLARE_OLECREATE_EX](#declare_olecreate_ex)|Объявляет фабрику класса для страницы управления или свойства OLE.|
|[IMPLEMENT_OLECREATE_EX](#implement_olecreate_ex)|Реализует `GetClassID` функцию управления и объявляет экземпляр фабрики класса.|
|[BEGIN_OLEFACTORY](#begin_olefactory)|Начинается декларирование любых функций лицензирования.|
|[END_OLEFACTORY](#end_olefactory)|Завершает декларирование любых функций лицензирования.|
|[AfxVerifyLicFile](#afxverifylicfile)|Проверяет, лицензируется ли элемент управления на использование на определенном компьютере.|

## <a name="declare_olecreate_ex"></a><a name="declare_olecreate_ex"></a>DECLARE_OLECREATE_EX

Объявляет фабрику класса `GetClassID` и функцию элемента вашего класса управления.

```
DECLARE_OLECREATE_EX(class_name)
```

### <a name="parameters"></a>Параметры

*class_name*<br/>
Название класса управления.

### <a name="remarks"></a>Remarks

Используйте этот макрос в файле заголовка заголовка класса управления для элемента управления, который не поддерживает лицензирование.

Обратите внимание, что этот макрос служит той же цели, что и следующий пример кода:

[!code-cpp[NVC_MFCAxCtl#14](../../mfc/reference/codesnippet/cpp/class-factories-and-licensing_1.h)]

### <a name="requirements"></a>Требования

  **Заголовок** afxctl.h

## <a name="implement_olecreate_ex"></a><a name="implement_olecreate_ex"></a>IMPLEMENT_OLECREATE_EX

Реализует фабрику классов элемента управления и функцию члена [GetClassID](../../mfc/reference/colecontrol-class.md#getclassid) вашего класса управления.

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
Название класса страницы свойства управления.

*external_name*<br/>
Имя объекта, подверженное приложениям.

*l, w1, w2, b1, b2, b3, b4, b5, b6, b7, b8*<br/>
Компоненты CLSID класса. Подробнее об этих параметрах читайте в [IMPLEMENT_OLECREATE.](run-time-object-model-services.md#implement_olecreate)

### <a name="remarks"></a>Remarks

Этот макрос должен отображаться в файле реализации для любого класса управления, использующем макрос DECLARE_OLECREATE_EX или BEGIN_OLEFACTORY и END_OLEFACTORY макросов. Внешнее имя является идентификатором управления OLE, который подвергается воздействию других приложений. Контейнеры используют это имя для запроса объекта этого класса управления.

### <a name="requirements"></a>Требования

  **Заголовок** afxctl.h

## <a name="begin_olefactory"></a><a name="begin_olefactory"></a>BEGIN_OLEFACTORY

Начинается объявление фабрики класса в файле заголовка вашего класса управления.

```
BEGIN_OLEFACTORY(class_name)
```

### <a name="parameters"></a>Параметры

*class_name*<br/>
Упогоняет название класса управления, чей класс фабрики это.

### <a name="remarks"></a>Remarks

Объявления о функциях лицензирования фабрик класса должны начинаться сразу же после BEGIN_OLEFACTORY.

### <a name="requirements"></a>Требования

  **Заголовок** afxctl.h

## <a name="end_olefactory"></a><a name="end_olefactory"></a>END_OLEFACTORY

Завершает объявление фабрики класса вашего элемента управления.

```
END_OLEFACTORY(class_name)
```

### <a name="parameters"></a>Параметры

*class_name*<br/>
Название класса управления, чей класс фабрики это.

### <a name="requirements"></a>Требования

  **Заголовок** afxctl.h

## <a name="afxverifylicfile"></a><a name="afxverifylicfile"></a>AfxVerifyLicFile

Вызовите эту функцию, чтобы `pszLicFileName` убедиться, что файл лицензии, названный, действителен для управления OLE.

```
BOOL AFXAPI AfxVerifyLicFile(
    HINSTANCE  hInstance,
    LPCTSTR  pszLicFileName,
    LPOLESTR  pszLicFileContents,
    UINT cch = -1);
```

### <a name="parameters"></a>Параметры

*hInstance*<br/>
Ручка экземпляра DLL, связанная с лицензированным управлением.

*pszLicFileName*<br/>
Указывает на строку символов с нулевым завершением, содержащую имя файла лицензии.

*pszLicFileКонтенты*<br/>
Указывает на последовательность байт, которая должна соответствовать последовательности, найденной в начале файла лицензии.

*Cch*<br/>
Количество символов в *pszLicFileContents .*

### <a name="return-value"></a>Возвращаемое значение

Nonzero, если лицензионный файл существует и начинается с последовательности символов в *pszLicFileContents;* в противном случае 0.

### <a name="remarks"></a>Remarks

Если *cch* -1, эта функция использует:

[!code-cpp[NVC_MFC_Utilities#36](../../mfc/codesnippet/cpp/class-factories-and-licensing_2.cpp)]

### <a name="requirements"></a>Требования

  **Заголовок** afxctl.h

## <a name="see-also"></a>См. также раздел

[Макросы и глобальные объекты](../../mfc/reference/mfc-macros-and-globals.md)
