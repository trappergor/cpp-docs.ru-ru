---
title: Регистрация элементов управления OLE
ms.date: 11/04/2016
helpviewer_keywords:
- registering OLE controls
- OLE controls [MFC], registering
ms.assetid: 73c45b7f-7dbc-43f5-bd17-dd77c6acec72
ms.openlocfilehash: 2f2d7872e8b9369b5eef283e5b52a54c29afd563
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81372969"
---
# <a name="registering-ole-controls"></a>Регистрация элементов управления OLE

Элементы управления OLE, как и другие объекты сервера OLE, могут быть доступны другим приложениям, осведомленным о OLE. Это достигается путем регистрации библиотеки и класса типа элемента управления.

Следующие функции позволяют добавлять и удалять класс управления, страницы свойств и библиотеку введите тип ы в базе данных регистрации Windows:

### <a name="registering-ole-controls"></a>Регистрация элементов управления OLE

|||
|-|-|
|[AfxOleRegisterControlClass](#afxoleregistercontrolclass)|Добавляет класс управления в базу данных регистрации.|
|[AfxOleRegisterPropertyPageClass](#afxoleregisterpropertypageclass)|Добавляет страницу контрольного свойства в базу данных регистрации.|
|[AfxOleRegisterTypeLib](#afxoleregistertypelib)|Добавляет библиотеку типа элемента управления в базу данных регистрации.|
|[AfxOleUnregisterClass](#afxoleunregisterclass)|Удаляет класс управления или класс страницы свойств из базы данных регистрации.|
|[AfxOleUnregisterTypeLib](#afxoleunregistertypelib)|Удаляет библиотеку типа элемента управления из базы данных регистрации.|

`AfxOleRegisterTypeLib`обычно вызывается в реализации `DllRegisterServer`управления DLL . Аналогичным `AfxOleUnregisterTypeLib` образом, `DllUnregisterServer`называется . `AfxOleRegisterControlClass`, `AfxOleRegisterPropertyPageClass`и `AfxOleUnregisterClass` обычно называются `UpdateRegistry` функцией элемента фабрики класса управления или страницы свойств.

## <a name="afxoleregistercontrolclass"></a><a name="afxoleregistercontrolclass"></a>AfxOleRegisterControlClass

Регистрирует класс управления с базой данных регистрации Windows.

```
BOOL AFXAPI AfxOleRegisterControlClass(
    HINSTANCE hInstance,
    REFCLSID clsid,
    LPCTSTR pszProgID,
    UINT idTypeName,
    UINT idBitmap,
    int nRegFlags,
    DWORD dwMiscStatus,
    REFGUID tlid,
    WORD wVerMajor,
    WORD wVerMinor);
```

### <a name="parameters"></a>Параметры

*hInstance*<br/>
Рукоятки экземпляра модуля, связанного с классом управления.

*clsid*<br/>
Уникальный идентификатор класса управления.

*pszProgID*<br/>
Уникальный идентификатор программы управления.

*idTypeName*<br/>
Идентификатор ресурса строки, содержащий имя для элемента управления, читаемое для пользователя.

*idBitmap*<br/>
Идентификатор ресурса битной карты, используемый для представления управления OLE в панели инструментов или палитре.

*nRegFlags*<br/>
Содержит один или несколько из следующих флагов:

- `afxRegInsertable`Позволяет элементуправления отображаться в диалоговом окне объекта вставки для объектов OLE.

- `afxRegApartmentThreading`Устанавливает модель резьбы в реестре на ThreadingModel-Квартира.

- `afxRegFreeThreading`Устанавливает модель потоков в реестре на ThreadingModel-Free.

   Вы можете объединить `afxRegApartmentThreading` два `afxRegFreeThreading` флага и установить ThreadingModel-Оба. Подробнее о регистрации моделей потоков читайте в [см. InprocServer32.](/windows/win32/com/inprocserver32)

> [!NOTE]
> В версиях MFC до MFC 4.2 параметр **int** *nRegFlags* был параметром BOOL, *bInsertable,* который позволял или отменял элемент управления, который должен быть вставлен из окна диалога объекта вставки.

*dwMiscStatus*<br/>
Содержит один или несколько флагов следующих статусов (для описания флагов см. перечисление OLEMISC в SDK Windows):

- OLEMISC_RECOMPOSEONRESIZE

- OLEMISC_ONLYICONIC

- OLEMISC_INSERTNOTREPLACE

- OLEMISC_STATIC

- OLEMISC_CANTLINKINSIDE

- OLEMISC_CANLINKBYOLE1

- OLEMISC_ISLINKOBJECT

- OLEMISC_INSIDEOUT

- OLEMISC_ACTIVATEWHENVISIBLE

- OLEMISC_RENDERINGISDEVICEINDEPENDENT

- OLEMISC_INVISIBLEATRUNTIME

- OLEMISC_ALWAYSRUN

- OLEMISC_ACTSLIKEBUTTON

- OLEMISC_ACTSLIKELABEL

- OLEMISC_NOUIACTIVATE

- OLEMISC_ALIGNABLE

- OLEMISC_IMEMODE

- OLEMISC_SIMPLEFRAME

- OLEMISC_SETCLIENTSITEFIRST

*tlid*<br/>
Уникальный идентификатор класса управления.

*wVerMajor*<br/>
Основной номер версии класса управления.

*wVerMinor*<br/>
Номер незначительной версии класса управления.

### <a name="return-value"></a>Возвращаемое значение

Nonzero, если контрольный класс был зарегистрирован; в противном случае 0.

### <a name="remarks"></a>Remarks

Это позволяет использовать элементуправления контейнерами, которые являются OL-контролем. `AfxOleRegisterControlClass`обновляет реестр с именем и местоположением элемента управления в системе, а также устанавливает модель потоков, которую элемент поддержки поддерживает в реестре. Для получения дополнительной информации [см. Техническое примечание 64](../../mfc/tn064-apartment-model-threading-in-activex-controls.md), "Квартира-модель резьбы в OLE управления", и [о процессах и потоках](/windows/win32/ProcThread/about-processes-and-threads) в Windows SDK.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCAxCtl#11](../../mfc/reference/codesnippet/cpp/registering-ole-controls_1.cpp)]

Вышеприведенный пример `AfxOleRegisterControlClass` демонстрирует, как называется с флагом для вставки и флаг для квартиры модели ORed вместе, чтобы создать шестой параметр:

[!code-cpp[NVC_MFCAxCtl#12](../../mfc/reference/codesnippet/cpp/registering-ole-controls_2.cpp)]

Элемент управления будет отображаться в диалоговом окне объекта вставки для включенных контейнеров, и это будет знать модель квартиры. Элементы управления, осведомленные о модели квартиры, должны гарантировать, что статические данные класса защищены блокировками, так что в то время как элемент управления в одной квартире имеет доступ к статическим данным, он не отключается планировщиком до их завершения, а другой экземпляр того же класса начинает использовать те же статические данные. Любые доступы к статическим данным будут окружены критическим кодом раздела.

### <a name="requirements"></a>Требования

  **Заголовок** afxctl.h

## <a name="afxoleregisterpropertypageclass"></a><a name="afxoleregisterpropertypageclass"></a>AfxOleRegisterPropertyPageClass

Регистрирует класс страницы недвижимости в базе данных регистрации Windows.

```
BOOL AFXAPI AfxOleRegisterPropertyPageClass(
   HINSTANCE hInstance,
   REFCLSID  clsid,
   UINT idTypeName,
   int nRegFlags);
```

### <a name="parameters"></a>Параметры

*hInstance*<br/>
Ручка экземпляра модуля, связанная с классом страницы свойств.

*clsid*<br/>
Уникальный идентификатор класса страницы свойств.

*idTypeName*<br/>
Идентификатор ресурса строки, содержащий читаемое пользователем имя для страницы свойств.

*nRegFlags*<br/>
Может содержать флаг:

- `afxRegApartmentThreading`Устанавливает модель резьбы в реестре на ThreadingModel и Апартаменты.

> [!NOTE]
> В версиях MFC до MFC 4.2 параметр **int** *nRegFlags* был недоступен. Обратите внимание `afxRegInsertable` также, что флаг не является допустимым вариантом для страниц свойств и вызовет ASSERT в MFC, если он установлен

### <a name="return-value"></a>Возвращаемое значение

Nonzero, если контрольный класс был зарегистрирован; в противном случае 0.

### <a name="remarks"></a>Remarks

Это позволяет использовать страницу свойств контейнерами, которые знают OL-контроль. `AfxOleRegisterPropertyPageClass`обновляет реестр с именем страницы свойства и его местоположением в системе, а также устанавливает модель потоков, которую поддерживает элемент управления в реестре. Для получения дополнительной информации [см. Техническое примечание 64](../../mfc/tn064-apartment-model-threading-in-activex-controls.md), "Квартира-модель резьбы в OLE управления", и [о процессах и потоках](/windows/win32/ProcThread/about-processes-and-threads) в Windows SDK.

### <a name="requirements"></a>Требования

  **Заголовок** afxctl.h

## <a name="afxoleregistertypelib"></a><a name="afxoleregistertypelib"></a>AfxOleRegisterTypeLib

Регистрирует библиотеку типов с базой данных регистрации Windows и позволяет использовать библиотеку типов другими контейнерами, которые соответствуют информации OL-управления.

```
BOOL AfxOleRegisterTypeLib(
    HINSTANCE hInstance,
    REFGUID tlid,
    LPCTSTR pszFileName = NULL,
    LPCTSTR pszHelpDir  = NULL);
```

### <a name="parameters"></a>Параметры

*hInstance*<br/>
Обработка экземпляра приложения, связанная с библиотекой типов.

*tlid*<br/>
Уникальный идентификатор библиотеки типов.

*pszFileName*<br/>
Указывает на дополнительное имя файла локализованной библиотеки типа (. TLB) файл для управления.

*pszHelpDir*<br/>
Название каталога, в котором можно найти файл справки для библиотеки типов. Если NULL, файл справки предполагается в том же каталоге, что и сама библиотека типов.

### <a name="return-value"></a>Возвращаемое значение

Nonzero, если библиотека типа была зарегистрирована; в противном случае 0.

### <a name="remarks"></a>Remarks

Эта функция обновляет реестр с именем библиотеки типа и его местоположением в системе.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCAutomation#7](../../mfc/codesnippet/cpp/registering-ole-controls_3.cpp)]

[!code-cpp[NVC_MFCAutomation#8](../../mfc/codesnippet/cpp/registering-ole-controls_4.cpp)]

### <a name="requirements"></a>Требования

  **Заголовок** afxdisp.h

## <a name="afxoleunregisterclass"></a><a name="afxoleunregisterclass"></a>AfxOleUnregisterClass

Удаляет запись в классе управления или страницы свойств из базы данных регистрации Windows.

```
BOOL AFXAPI AfxOleUnregisterClass(REFCLSID clsID, LPCSTR pszProgID);
```

### <a name="parameters"></a>Параметры

*Clsid*<br/>
Уникальный идентификатор класса страницы управления или свойства.

*pszProgID*<br/>
Уникальный идентификатор программы элемента управления или страницы свойства.

### <a name="return-value"></a>Возвращаемое значение

Nonzero, если класс страницы управления или свойства был успешно незарегистрирован; в противном случае 0.

### <a name="requirements"></a>Требования

  **Заголовок** afxctl.h

## <a name="afxoleunregistertypelib"></a><a name="afxoleunregistertypelib"></a>AfxOleUnregisterTypeLib

Вызовите эту функцию, чтобы удалить запись библиотеки типа из базы данных регистрации Windows.

```
BOOL AFXAPI AfxOleUnregisterTypeLib(REFGUID tlID);
```

### <a name="parameters"></a>Параметры

*tlID*<br/>
Уникальный идентификатор библиотеки типов.

### <a name="return-value"></a>Возвращаемое значение

Nonzero, если библиотека типа была успешно незарегистрирована; в противном случае 0.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCAxCtl#13](../../mfc/reference/codesnippet/cpp/registering-ole-controls_5.cpp)]

### <a name="requirements"></a>Требования

  **Заголовок** afxdisp.h

## <a name="see-also"></a>См. также раздел

[Макросы и глобальные объекты](../../mfc/reference/mfc-macros-and-globals.md)
