---
title: FtmBase - класс
ms.date: 10/03/2018
ms.topic: reference
f1_keywords:
- ftm/Microsoft::WRL::FtmBase
- ftm/Microsoft::WRL::FtmBaseCreateGlobalInterfaceTable
- ftm/Microsoft::WRL::FtmBase::DisconnectObject
- ftm/Microsoft::WRL::FtmBase::FtmBase
- ftm/Microsoft::WRL::FtmBase::GetMarshalSizeMax
- ftm/Microsoft::WRL::FtmBase::GetUnmarshalClass
- ftm/Microsoft::WRL::FtmBase::MarshalInterface
- ftm/Microsoft::WRL::FtmBase::marshaller_
- ftm/Microsoft::WRL::FtmBase::ReleaseMarshalData
- ftm/Microsoft::WRL::FtmBase::UnmarshalInterface
helpviewer_keywords:
- Microsoft::WRL::FtmBase class
- Microsoft::WRL::FtmBase::CreateGlobalInterfaceTable method
- Microsoft::WRL::FtmBase::DisconnectObject method
- Microsoft::WRL::FtmBase::FtmBase, constructor
- Microsoft::WRL::FtmBase::GetMarshalSizeMax method
- Microsoft::WRL::FtmBase::GetUnmarshalClass method
- Microsoft::WRL::FtmBase::MarshalInterface method
- Microsoft::WRL::FtmBase::marshaller_ data member
- Microsoft::WRL::FtmBase::ReleaseMarshalData method
- Microsoft::WRL::FtmBase::UnmarshalInterface method
ms.assetid: 275f3b71-2975-4f92-89e7-d351e96496df
ms.openlocfilehash: d37cdddda8cf8894016ed80b9055fe106b1600f7
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81371517"
---
# <a name="ftmbase-class"></a>FtmBase - класс

Представляет свободнопоточный объект маршаллера.

## <a name="syntax"></a>Синтаксис

```cpp
class FtmBase :
    public Microsoft::WRL::Implements<
        Microsoft::WRL::RuntimeClassFlags<WinRtClassicComMix>,
        Microsoft::WRL::CloakedIid<IMarshal>
    >;
```

## <a name="remarks"></a>Remarks

Для получения дополнительной [RuntimeClass Class](runtimeclass-class.md)информации см.

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

| Имя                         | Описание                                        |
| ---------------------------- | -------------------------------------------------- |
| [FtmBase::FtmBase](#ftmbase) | Инициализирует новый экземпляр класса `FtmBase`. |

### <a name="public-methods"></a>Открытые методы

| Имя                                                               | Описание                                                                                                                                                          |
| ------------------------------------------------------------------ | -------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| [FtmBase::CreateGlobalInterfaceTable](#createglobalinterfacetable) | Создает глобальную таблицу интерфейсов (GIT).                                                                                                                              |
| [FtmBase::DisconnectObject](#disconnectobject)                     | Принудительно освобождает все внешние соединения с объектом. Сервер объекта вызывает реализацию этого метода объекта до закрытия.                |
| [FtmBase::GetMarshalSizeMax](#getmarshalsizemax)                   | Получите верхнюю границу на количестве байтов, необходимых для маршала указанного указателя интерфейса на указанном объекте.                                                |
| [FtmBase:GetUnmarshalClass](#getunmarshalclass)                   | Получает CLSID, который COM использует, чтобы найти DLL, содержащий код для соответствующего прокси. COM загружает этот DLL для создания непрепренифицированного экземпляра прокси. |
| [FtmBase::MarshalInterface](#marshalinterface)                     | Записывает в поток данные, необходимые для инициализации прокси-объекта в процессе клиента.                                                                          |
| [FtmBase::ReleaseMarshalData](#releasemarshaldata)                 | Уничтожает пакет с маршалами.                                                                                                                                    |
| [FtmBase::UnmarshalInterface](#unmarshalinterface)                 | Инициализирует вновь созданный прокси и возвращает указатель интерфейса к этому прокси.                                                                                    |

### <a name="public-data-members"></a>Открытые члены данных

| Имя                                | Описание                                       |
| ----------------------------------- | ------------------------------------------------- |
| [FtmBase::marshaller_](#marshaller) | Содержит ссылку на свободного резьбового маршала. |

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`FtmBase`

## <a name="requirements"></a>Требования

**Заголовок:** ftm.h

**Пространство имен:** Microsoft::WRL

## <a name="ftmbasecreateglobalinterfacetable"></a><a name="createglobalinterfacetable"></a>FtmBase::CreateGlobalInterfaceTable

Создает глобальную таблицу интерфейсов (GIT).

```cpp
static HRESULT CreateGlobalInterfaceTable(
   __out IGlobalInterfaceTable **git
);
```

### <a name="parameters"></a>Параметры

*Git*<br/>
Когда эта операция завершается, указатель на глобальную таблицу интерфейса.

### <a name="return-value"></a>Возвращаемое значение

Значение S_OK, если операция завершилась успешно; в противном случае — значение HRESULT, указывающее на ошибку.

### <a name="remarks"></a>Remarks

Для получения дополнительной `IGlobalInterfaceTable` информации, `COM Interfaces` см. `COM Reference` тему в подтеме темы в библиотеке MSDN.

## <a name="ftmbasedisconnectobject"></a><a name="disconnectobject"></a>FtmBase::DisconnectObject

Принудительно освобождает все внешние соединения с объектом. Сервер объекта вызывает реализацию этого метода объекта до закрытия.

```cpp
STDMETHODIMP DisconnectObject(
   __in DWORD dwReserved
) override;
```

### <a name="parameters"></a>Параметры

*dwReserved*<br/>
Зарезервировано для будущего использования; должно иметь значение нуль.

### <a name="return-value"></a>Возвращаемое значение

Значение S_OK, если операция завершилась успешно; в противном случае — значение HRESULT, указывающее на ошибку.

## <a name="ftmbaseftmbase"></a><a name="ftmbase"></a>FtmBase::FtmBase

Инициализирует новый экземпляр класса `FtmBase`.

```cpp
FtmBase();
```

## <a name="ftmbasegetmarshalsizemax"></a><a name="getmarshalsizemax"></a>FtmBase::GetMarshalSizeMax

Получите верхнюю границу на количестве байтов, необходимых для маршала указанного указателя интерфейса на указанном объекте.

```cpp
STDMETHODIMP GetMarshalSizeMax(
   __in REFIID riid,
   __in_opt void *pv,
   __in DWORD dwDestContext,
   __reserved void *pvDestContext,
   __in DWORD mshlflags,
   __out DWORD *pSize
) override;
```

### <a name="parameters"></a>Параметры

*riid*<br/>
Ссылка на идентификатор интерфейса, который должен быть маршалом.

*Pv*<br/>
Указатель интерфейса, который будет маршализирован; может быть NULL.

*dwDestКонтекст*<br/>
Контекст назначения, где указанный интерфейс должен быть немаршализированным.

Укажите одно или несколько значений перечисления MSHCTX.

В настоящее время немаршалинг может произойти либо в другой квартире текущего процесса (MSHCTX_INPROC), либо в другом процессе на том же компьютере, что и текущий процесс (MSHCTX_LOCAL).

*pvDestContext*<br/>
Зарезервировано для использования в будущем; должны быть NULL.

*мфлагфлаги*<br/>
Пометить, следует ли передавать данные, которые должны быть переданы обратно в процесс клиента - типичный случай - или записать в глобальную таблицу, где он может быть извлечен несколькими клиентами. Укажите одно или несколько значений перечисления MSHLFLAGS.

*pSize*<br/>
Когда эта операция завершается, указатель на верхнюю границу на объем данных, которые будут записаны в поток маршала.

### <a name="return-value"></a>Возвращаемое значение

S_OK в случае успеха; в противном случае, E_FAIL или E_NOINTERFACE.

## <a name="ftmbasegetunmarshalclass"></a><a name="getunmarshalclass"></a>FtmBase:GetUnmarshalClass

Получает CLSID, который COM использует, чтобы найти DLL, содержащий код для соответствующего прокси. COM загружает этот DLL для создания непрепренифицированного экземпляра прокси.

```cpp
STDMETHODIMP GetUnmarshalClass(
   __in REFIID riid,
   __in_opt void *pv,
   __in DWORD dwDestContext,
   __reserved void *pvDestContext,
   __in DWORD mshlflags,
   __out CLSID *pCid
) override;
```

### <a name="parameters"></a>Параметры

*riid*<br/>
Ссылка на идентификатор интерфейса, который должен быть маршалом.

*Pv*<br/>
Указатель на интерфейс, который должен быть маршализирован; может быть NULL, если абонент не имеет указателя на нужный интерфейс.

*dwDestКонтекст*<br/>
Контекст назначения, где указанный интерфейс должен быть немаршализированным.

Укажите одно или несколько значений перечисления MSHCTX.

Немаршалирование может произойти либо в другой квартире текущего процесса (MSHCTX_INPROC), либо в другом процессе на том же компьютере, что и текущий процесс (MSHCTX_LOCAL).

*pvDestContext*<br/>
Зарезервировано для использования в будущем; должны быть NULL.

*мфлагфлаги*<br/>
Когда эта операция завершается, указатель на CLSID будет использоваться для создания прокси в клиентском процессе.

*pCid*

### <a name="return-value"></a>Возвращаемое значение

S_OK в случае успеха; в противном случае, S_FALSE.

## <a name="ftmbasemarshalinterface"></a><a name="marshalinterface"></a>FtmBase::MarshalInterface

Записывает в поток данные, необходимые для инициализации прокси-объекта в процессе клиента.

```cpp
STDMETHODIMP MarshalInterface(
   __in IStream *pStm,
   __in REFIID riid,
   __in_opt void *pv,
   __in DWORD dwDestContext,
   __reserved void *pvDestContext,
   __in DWORD mshlflags
) override;
```

### <a name="parameters"></a>Параметры

*pStm*<br/>
Указатель на поток, который будет использоваться во время маршала.

*riid*<br/>
Ссылка на идентификатор интерфейса, который должен быть маршалом. Он должен быть производным от интерфейса `IUnknown` .

*Pv*<br/>
Указатель на указатель интерфейса, который должен быть marshaled; может быть NULL, если абонент не имеет указателя на нужный интерфейс.

*dwDestКонтекст*<br/>
Контекст назначения, где указанный интерфейс должен быть немаршализированным.

Укажите одно или несколько значений перечисления MSHCTX.

Немаршалирование может произойти в другой квартире текущего процесса (MSHCTX_INPROC) или в другом процессе на том же компьютере, что и текущий процесс (MSHCTX_LOCAL).

*pvDestContext*<br/>
Зарезервировано для будущего использования; должно иметь значение нуль.

*мфлагфлаги*<br/>
Уточняется, должны ли данные, которые должны быть переданы в процесс клиента - типичный случай - или записаны на глобальную таблицу, где они могут быть получены несколькими клиентами.

### <a name="return-value"></a>Возвращаемое значение

S_OK Интерфейс указатель был успешно marshaled.

E_NOINTERFACE Указанный интерфейс не поддерживается.

STG_E_MEDIUMFULL Поток полон.

E_FAIL Операция не удалась.

## <a name="ftmbasemarshaller_"></a><a name="marshaller"></a>FtmBase::marshaller_

Содержит ссылку на свободного резьбового маршала.

```cpp
Microsoft::WRL::ComPtr<IMarshal> marshaller_; ;
```

## <a name="ftmbasereleasemarshaldata"></a><a name="releasemarshaldata"></a>FtmBase::ReleaseMarshalData

Уничтожает пакет с маршалами.

```cpp
STDMETHODIMP ReleaseMarshalData(
   __in IStream *pStm
) override;
```

### <a name="parameters"></a>Параметры

*pStm*<br/>
Указатель на поток, содержащий пакет данных, который будет уничтожен.

### <a name="return-value"></a>Возвращаемое значение

Значение S_OK, если операция завершилась успешно; в противном случае — значение HRESULT, указывающее на ошибку.

## <a name="ftmbaseunmarshalinterface"></a><a name="unmarshalinterface"></a>FtmBase::UnmarshalInterface

Инициализирует вновь созданный прокси и возвращает указатель интерфейса к этому прокси.

```cpp
STDMETHODIMP UnmarshalInterface(
   __in IStream *pStm,
   __in REFIID riid,
   __deref_out void **ppv
) override;
```

### <a name="parameters"></a>Параметры

*pStm*<br/>
Указатель на поток, из которого указатель интерфейса должен быть неmarshaled.

*riid*<br/>
Ссылка на идентификатор интерфейса, который должен быть немаршализированным.

*Ppv*<br/>
Когда эта операция завершается, адрес переменной указателя, которая получает указатель интерфейса, запрошенный в *riid*. Если эта операция успешна,*ppv* содержит запрошенный указатель интерфейса интерфейса, который будет неmarshaled.

### <a name="return-value"></a>Возвращаемое значение

S_OK в случае успеха; в противном случае, E_NOINTERFACE или E_FAIL.
