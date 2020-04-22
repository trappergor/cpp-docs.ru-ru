---
title: Класс CAtlModule
ms.date: 11/04/2016
f1_keywords:
- CAtlModule
- ATLBASE/ATL::CAtlModule
- ATLBASE/ATL::CAtlModule::CAtlModule
- ATLBASE/ATL::CAtlModule::AddCommonRGSReplacements
- ATLBASE/ATL::CAtlModule::AddTermFunc
- ATLBASE/ATL::CAtlModule::GetGITPtr
- ATLBASE/ATL::CAtlModule::GetLockCount
- ATLBASE/ATL::CAtlModule::Lock
- ATLBASE/ATL::CAtlModule::Term
- ATLBASE/ATL::CAtlModule::Unlock
- ATLBASE/ATL::CAtlModule::UpdateRegistryFromResourceD
- ATLBASE/ATL::CAtlModule::UpdateRegistryFromResourceDHelper
- ATLBASE/ATL::CAtlModule::UpdateRegistryFromResourceS
- ATLBASE/ATL::CAtlModule::m_libid
- ATLBASE/ATL::CAtlModule::m_pGIT
helpviewer_keywords:
- CAtlModule class
ms.assetid: 63fe02f1-4c4b-4e7c-ae97-7ad7b4252415
ms.openlocfilehash: cfc11a95a8d5d9354279f4c71698a6bc35c7aca7
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/22/2020
ms.locfileid: "81748617"
---
# <a name="catlmodule-class"></a>Класс CAtlModule

Этот класс предоставляет методы, используемые несколькими классами модулей ATL.

## <a name="syntax"></a>Синтаксис

```
class ATL_NO_VTABLE CAtlModule : public _ATL_MODULE
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CAtlModule::CAtlModule](#catlmodule)|Конструктор.|
|[CAtlModule:::CAtlModule](#dtor)|Деструктор|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CAtlModule::AddCommonRGSЗамены](#addcommonrgsreplacements)|Переопределить этот метод, чтобы добавить параметры в заменяемую карту замещения компонента реестра ATL (регистратор).|
|[CAtlModule::AddTermFunc](#addtermfunc)|Добавляет новую функцию, которая будет вызываться при завершении модуля.|
|[CAtlModule::GetGITPtr](#getgitptr)|Возвращает глобальный указатель интерфейса.|
|[CAtlModule::GetLockCount](#getlockcount)|Возвращает счет блокировки.|
|[CAtlModule::Блокировка](#lock)|Приравливывает количество блокировки.|
|[CAtlModule::Срок](#term)|Выпускает всех участников данных.|
|[CAtlModule::Разблокировка](#unlock)|Уменьшает на единицу счетчик блокировок.|
|[CAtlModule::UpdateRegistryFromResourced](#updateregistryfromresourced)|Запускает скрипт, содержащийся в указанном ресурсе, для регистрации или отрегистрации объекта.|
|[CAtlModule::UpdateRegistryFromResourceDHelper](#updateregistryfromresourcedhelper)|Этот метод вызывается `UpdateRegistryFromResourceD` для выполнения обновления реестра.|
|[CAtlModule::UpdateRegistryFromResources](#updateregistryfromresources)|Запускает скрипт, содержащийся в указанном ресурсе, для регистрации или отрегистрации объекта. Этот метод статически ссылается на компонент реестра ATL.|

### <a name="public-data-members"></a>Открытые члены данных

|Имя|Описание|
|----------|-----------------|
|[CAtlModule::m_libid](#m_libid)|Содержит GUID текущего модуля.|
|[CAtlModule::m_pGIT](#m_pgit)|Указатель на таблицу глобального интерфейса.|

## <a name="remarks"></a>Remarks

Этот класс используется [классом CAtlDllModuleT,](../../atl/reference/catldllmodulet-class.md) [классом CAtlExeModuleT](../../atl/reference/catlexemodulet-class.md)и [классом CAtlServiceModuleT](../../atl/reference/catlservicemodulet-class.md) для обеспечения поддержки DLL-приложений, приложений EXE и служб Windows, соответственно.

Для получения дополнительной информации о модулях в ATL, [см.](../../atl/atl-module-classes.md)

Этот класс заменяет устаревший [класс CComModule,](../../atl/reference/ccommodule-class.md) используемый в более ранних версиях ATL.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[_ATL_MODULE](atl-typedefs.md#_atl_module)

`CAtlModule`

## <a name="requirements"></a>Требования

**Заголовок:** atlbase.h

## <a name="catlmoduleaddcommonrgsreplacements"></a><a name="addcommonrgsreplacements"></a>CAtlModule::AddCommonRGSЗамены

Переопределить этот метод, чтобы добавить параметры в заменяемую карту замещения компонента реестра ATL (регистратор).

```
virtual HRESULT AddCommonRGSReplacements(IRegistrarBase* /* pRegistrar*/) throw() = 0;
```

### <a name="parameters"></a>Параметры

*pRegistrar*<br/>
Зарезервировано.

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK на успех, или ошибка HRESULT на отказ.

### <a name="remarks"></a>Remarks

Заменяемые параметры позволяют клиенту Регистратора указывать данные о времени выполнения. Для этого Регистратор поддерживает карту замены, в которую он вводит значения, связанные со сменными параметрами в скрипте. Регистратор делает эти записи во время выполнения.

Более подробная информация приводиткся в [теме «Использование сменных параметров » (Препроцессор регистратора).](../../atl/using-replaceable-parameters-the-registrar-s-preprocessor.md)

## <a name="catlmoduleaddtermfunc"></a><a name="addtermfunc"></a>CAtlModule::AddTermFunc

Добавляет новую функцию, которая будет вызываться при завершении модуля.

```
HRESULT AddTermFunc(_ATL_TERMFUNC* pFunc, DWORD_PTR dw) throw();
```

### <a name="parameters"></a>Параметры

*pFunc*<br/>
Указатель на функцию для добавления.

*dw*<br/>
Данные, определяемые пользователем, передаются функции.

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK на успех, или ошибка HRESULT на отказ.

## <a name="catlmodulecatlmodule"></a><a name="catlmodule"></a>CAtlModule::CAtlModule

Конструктор.

```
CAtlModule() throw();
```

### <a name="remarks"></a>Remarks

Инициализирует членов данных и инициирует критический раздел вокруг потока модуля.

## <a name="catlmodulecatlmodule"></a><a name="dtor"></a>CAtlModule:::CAtlModule

Деструктор

```
~CAtlModule() throw();
```

### <a name="remarks"></a>Remarks

Выпускает всех участников данных.

## <a name="catlmodulegetgitptr"></a><a name="getgitptr"></a>CAtlModule::GetGITPtr

Извлекает указатель в таблицу глобального интерфейса.

```
virtual HRESULT GetGITPtr(IGlobalInterfaceTable** ppGIT) throw();
```

### <a name="parameters"></a>Параметры

*ppGIT*<br/>
Указатель на переменную, которая получит указатель на глобальную таблицу интерфейсов.

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK на успех, или код ошибки при сбое. E_POINTER возвращается, если *ppGIT* равен NULL.

### <a name="remarks"></a>Remarks

Если объект Таблица глобального интерфейса не существует, он создается, и его адрес хранится в переменной [CAtlModule::m_pGIT](#m_pgit).

В отладках сборки будет возникать ошибка утверждения, если *ppGIT* равен NULL, или если не удается получить указатель таблицы глобального интерфейса.

[См. IGlobalInterfaceTable](/windows/win32/api/objidl/nn-objidl-iglobalinterfacetable) для получения информации о глобальной таблице интерфейсов.

## <a name="catlmodulegetlockcount"></a><a name="getlockcount"></a>CAtlModule::GetLockCount

Возвращает счет блокировки.

```
virtual LONG GetLockCount() throw();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает счет блокировки. Это значение может быть полезно для диагностики и отладки.

## <a name="catlmodulelock"></a><a name="lock"></a>CAtlModule::Блокировка

Приравливывает количество блокировки.

```
virtual LONG Lock() throw();
```

### <a name="return-value"></a>Возвращаемое значение

Приравливывает количество блокировки и возвращает обновленное значение. Это значение может быть полезно для диагностики и отладки.

## <a name="catlmodulem_libid"></a><a name="m_libid"></a>CAtlModule::m_libid

Содержит GUID текущего модуля.

```
static GUID m_libid;
```

## <a name="catlmodulem_pgit"></a><a name="m_pgit"></a>CAtlModule::m_pGIT

Указатель на таблицу глобального интерфейса.

```
IGlobalInterfaceTable* m_pGIT;
```

## <a name="catlmoduleterm"></a><a name="term"></a>CAtlModule::Срок

Выпускает всех участников данных.

```cpp
void Term() throw();
```

### <a name="remarks"></a>Remarks

Выпускает всех участников данных. Этот метод называется деструктором.

## <a name="catlmoduleunlock"></a><a name="unlock"></a>CAtlModule::Разблокировка

Уменьшает на единицу счетчик блокировок.

```
virtual LONG Unlock() throw();
```

### <a name="return-value"></a>Возвращаемое значение

Декретирует количество блокировки и возвращает обновленное значение. Это значение может быть полезно для диагностики и отладки.

## <a name="catlmoduleupdateregistryfromresourced"></a><a name="updateregistryfromresourced"></a>CAtlModule::UpdateRegistryFromResourced

Запускает скрипт, содержащийся в указанном ресурсе, для регистрации или отрегистрации объекта.

```
HRESULT WINAPI UpdateRegistryFromResourceD(
    UINT nResID,
    BOOL bRegister,
    struct _ATL_REGMAP_ENTRY* pMapEntries = NULL) throw();

HRESULT WINAPI UpdateRegistryFromResourceD(
    LPCTSTR lpszRes,
    BOOL bRegister,
    struct _ATL_REGMAP_ENTRY* pMapEntries = NULL) throw();
```

### <a name="parameters"></a>Параметры

*lpszRes*<br/>
Имя ресурса.

*nResID*<br/>
Идентификатор ресурса.

*bРегистрация*<br/>
TRUE, если объект должен быть зарегистрирован; FALSE в противном случае.

*pMapE записи*<br/>
Указатель на значения замены карты, связанные со сменными параметрами скрипта. ATL автоматически использует %Module%. Для использования дополнительных сменных параметров см. [CAtlModule::AddCommonRGSЗамены](#addcommonrgsreplacements). В противном случае используйте значение NULL по умолчанию.

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK на успех, или ошибка HRESULT на отказ.

### <a name="remarks"></a>Remarks

Запускает скрипт, содержащийся в ресурсе, указанном *lpszRes или nResID.* Если *bRegister* является правдой, этот метод регистрирует объект в системном реестре; в противном случае он удаляет объект из реестра.

Чтобы статически ссылку на компонент реестра ATL (регистратор), [см. CAtlModule::UpdateRegistryFromResourceS](#updateregistryfromresources).

Этот метод вызывает [CAtlModule::UpdateRegistryFromResourceDHelper](#updateregistryfromresourcedhelper) и [IRegistrar::ResourceUnregister](iregistrar-class.md#resourceunregister).

## <a name="catlmoduleupdateregistryfromresourcedhelper"></a><a name="updateregistryfromresourcedhelper"></a>CAtlModule::UpdateRegistryFromResourceDHelper

Этот метод вызывается `UpdateRegistryFromResourceD` для выполнения обновления реестра.

```
inline HRESULT WINAPI UpdateRegistryFromResourceDHelper(
    LPCOLESTR lpszRes,
    BOOL bRegister,
    struct _ATL_REGMAP_ENTRY* pMapEntries = NULL) throw();
```

### <a name="parameters"></a>Параметры

*lpszRes*<br/>
Имя ресурса.

*bРегистрация*<br/>
Указывает, должен ли объект быть зарегистрирован.

*pMapE записи*<br/>
Указатель на значения замены карты, связанные со сменными параметрами скрипта. ATL автоматически использует %Module%. Для использования дополнительных сменных параметров см. [CAtlModule::AddCommonRGSЗамены](#addcommonrgsreplacements). В противном случае используйте значение NULL по умолчанию.

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK на успех, или ошибка HRESULT на отказ.

### <a name="remarks"></a>Remarks

Этот метод обеспечивает реализацию [CAtlModule::UpdateRegistryFromResourceD](#updateregistryfromresourced).

## <a name="catlmoduleupdateregistryfromresources"></a><a name="updateregistryfromresources"></a>CAtlModule::UpdateRegistryFromResources

Запускает скрипт, содержащийся в указанном ресурсе, для регистрации или отрегистрации объекта. Этот метод статически ссылается на компонент реестра ATL.

```
HRESULT WINAPI UpdateRegistryFromResourceS(
    UINT nResID,
    BOOL bRegister,
    struct _ATL_REGMAP_ENTRY* pMapEntries = NULL) throw();

HRESULT WINAPI UpdateRegistryFromResourceS(
    LPCTSTR lpszRes,
    BOOL bRegister,
    struct _ATL_REGMAP_ENTRY* pMapEntries = NULL) throw();
```

### <a name="parameters"></a>Параметры

*nResID*<br/>
Идентификатор ресурса.

*lpszRes*<br/>
Имя ресурса.

*bРегистрация*<br/>
Указывает, должен ли быть зарегистрирован скрипт ресурса.

*pMapE записи*<br/>
Указатель на значения замены карты, связанные со сменными параметрами скрипта. ATL автоматически использует %Module%. Для использования дополнительных сменных параметров см. [CAtlModule::AddCommonRGSЗамены](#addcommonrgsreplacements). В противном случае используйте значение NULL по умолчанию.

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK на успех, или ошибка HRESULT на отказ.

### <a name="remarks"></a>Remarks

Как и [CAtlModule::UpdateRegistryFromResourceD,](#updateregistryfromresourced) за исключением `CAtlModule::UpdateRegistryFromResourceS` создает статическую ссылку на компонент реестра ATL (регистратор).

## <a name="see-also"></a>См. также раздел

[_ATL_MODULE](atl-typedefs.md#_atl_module)<br/>
[Общие сведения о классах](../../atl/atl-class-overview.md)<br/>
[Классы модулей](../../atl/atl-module-classes.md)<br/>
[Компонент реестра (регистратор)](../../atl/atl-registry-component-registrar.md)
