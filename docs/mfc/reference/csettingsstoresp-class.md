---
title: Класс CSettingsStoreSP | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CSettingsStoreSP
- AFXSETTINGSSTORE/CSettingsStoreSP
- AFXSETTINGSSTORE/CSettingsStoreSP::CSettingsStoreSP
- AFXSETTINGSSTORE/CSettingsStoreSP::Create
- AFXSETTINGSSTORE/CSettingsStoreSP::SetRuntimeClass
dev_langs:
- C++
helpviewer_keywords:
- CSettingsStoreSP [MFC], CSettingsStoreSP
- CSettingsStoreSP [MFC], Create
- CSettingsStoreSP [MFC], SetRuntimeClass
ms.assetid: bcd37f40-cfd4-4d17-a5ce-3bfabe995dcc
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: c2b80ab73c41d455b0715f15034b54197672b95d
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46424876"
---
# <a name="csettingsstoresp-class"></a>Класс CSettingsStoreSP

`CSettingsStoreSP` Класс — это вспомогательный класс, который можно использовать для создания экземпляров [CSettingsStore Class](../../mfc/reference/csettingsstore-class.md).

## <a name="syntax"></a>Синтаксис

```
class CSettingsStoreSP
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CSettingsStoreSP::CSettingsStoreSP](#csettingsstoresp)|Создает объект `CSettingsStoreSP`.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CSettingsStoreSP::Create](#create)|Создает экземпляр класса, который является производным от `CSettingsStore`.|
|[CSettingsStoreSP::SetRuntimeClass](#setruntimeclass)|Задает класс среды выполнения. `Create` Метод использует класс среды выполнения, чтобы определить, какой класс объектов для создания.|

### <a name="data-members"></a>Элементы данных

|name|Описание|
|----------|-----------------|
|`m_dwUserData`|Пользовательские данные, хранящиеся в `CSettingsStoreSP` объекта. Вы указали эти данные в конструкторе класса `CSettingsStoreSP` объекта.|
|`m_pRegistry`|`CSettingsStore`-Производного объекта, `Create` методом.|

## <a name="remarks"></a>Примечания

Можно использовать `CSettingsStoreSP` перенаправить все операции с реестром MFC в другие расположения, например XML-файл или базу данных. Для этого выполните следующие действия:

1. Создайте класс (такие как `CMyStore`) и сделайте его производным от `CSettingsStore`.

1. Используйте [DECLARE_DYNCREATE](run-time-object-model-services.md#declare_dyncreate) и [IMPLEMENT_DYNCREATE](run-time-object-model-services.md#implement_dyncreate) макросы с пользовательским `CSettingsStore` класса, чтобы включить динамическое создание.

1. Переопределение виртуальных функций и реализовать `Read` и `Write` функций в пользовательский класс. Реализуйте другие функциональные возможности для чтения и записи данных в нужное расположение.

1. В приложении, вызовите `CSettingsStoreSP::SetRuntimeClass` и передавать в указатель на [структура CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) получен из вашего класса.

Каждый раз, когда платформа обычно получит доступ к реестру, она будет динамически создать экземпляр пользовательского класса и использовать его для чтения или записи данных.

`CSettingsStoreSP::SetRuntimeClass` использует глобальной статической переменной. Таким образом только один пользовательский магазин доступен одновременно.

## <a name="requirements"></a>Требования

**Заголовок:** afxsettingsstore.h

##  <a name="create"></a>  CSettingsStoreSP::Create

Создает новый экземпляр объекта, который является производным от [CSettingsStore Class](../../mfc/reference/csettingsstore-class.md).

```
CSettingsStore& CSettingsStoreSP Create(
    BOOL bAdmin,
    BOOL bReadOnly);
```

### <a name="parameters"></a>Параметры

*bAdmin*<br/>
[in] Логический параметр, который определяет, является ли `CSettingsStore` объект создается в режиме администратора.

*bReadOnly*<br/>
[in] Логический параметр, который определяет, является ли `CSettingsStore` объекта создается для доступа только для чтения.

### <a name="return-value"></a>Возвращаемое значение

Ссылку на только что созданный `CSettingsStore` объекта.

### <a name="remarks"></a>Примечания

Можно использовать метод [CSettingsStoreSP::SetRuntimeClass](#setruntimeclass) для определения типа объекта `CSettingsStoreSP::Create` будет создан. По умолчанию этот метод создает `CSettingsStore` объекта.

Если вы создаете `CSettingsStore` объект в режиме администратора, расположение по умолчанию для всех операций доступа реестра HKEY_LOCAL_MACHINE. В противном случае по умолчанию для всех доступ к реестру располагается HKEY_CURRENT_USER.

Если *bAdmin* имеет значение TRUE, приложение должно иметь права администрирования. В противном случае он завершится ошибкой при попытке доступа к реестру.

### <a name="example"></a>Пример

Следующий пример демонстрирует, как использовать `Create` метод `CSettingsStoreSP` класса.

[!code-cpp[NVC_MFC_RibbonApp#33](../../mfc/reference/codesnippet/cpp/csettingsstoresp-class_1.cpp)]

##  <a name="csettingsstoresp"></a>  CSettingsStoreSP::CSettingsStoreSP

Создает [класс CSettingsStoreSP](../../mfc/reference/csettingsstoresp-class.md) объекта.

```
CSettingsStoreSP::CSettingsStoreSP(DWORD dwUserData = 0);
```

### <a name="parameters"></a>Параметры

*dwUserData*<br/>
[in] Определяемые пользователем данные, `CSettingsStoreSP` объекта хранилища.

### <a name="remarks"></a>Примечания

`CSettingsStoreSP` Объект сохраняет данные из *dwUserData* в защищенный член переменной `m_dwUserData`.

##  <a name="setruntimeclass"></a>  CSettingsStoreSP::SetRuntimeClass

Задает класс среды выполнения. Метод [CSettingsStoreSP::Create](#create) использует класс среды выполнения для определения типа создаваемого объекта.

```
static BOOL __stdcall CSettingsStoreSP::SetRuntimeClass(CRuntimeClass* pRTI);
```

### <a name="parameters"></a>Параметры

*pRTI*<br/>
[in] Указатель на сведения о классе среды выполнения для класса, производного от [CSettingsStore Class](../../mfc/reference/csettingsstore-class.md).

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если выполнение прошло успешно; Значение FALSE, если класс, указанный параметром *pRTI* не является производным от `CSettingsStore`.

### <a name="remarks"></a>Примечания

Можно использовать [класс CSettingsStoreSP](../../mfc/reference/csettingsstoresp-class.md) создавать производные классы от `CSettingsStore`. Используйте метод `SetRuntimeClass` Если вы хотите создать объекты пользовательского класса, который является производным от `CSettingsStore`.

## <a name="see-also"></a>См. также

[Классы](../../mfc/reference/mfc-classes.md)<br/>
[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Класс CSettingsStore](../../mfc/reference/csettingsstore-class.md)
