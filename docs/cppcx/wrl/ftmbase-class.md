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
ms.openlocfilehash: fb7f103d8ea647f554d9bbf26c2e218d34f6b1ff
ms.sourcegitcommit: 5cecccba0a96c1b4ccea1f7a1cfd91f259cc5bde
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/01/2019
ms.locfileid: "58786036"
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

## <a name="remarks"></a>Примечания

Дополнительные сведения см. в разделе [класс RuntimeClass](runtimeclass-class.md).

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

| name                         | Описание                                        |
| ---------------------------- | -------------------------------------------------- |
| [FtmBase::FtmBase](#ftmbase) | Инициализирует новый экземпляр класса `FtmBase`. |

### <a name="public-methods"></a>Открытые методы

| name                                                               | Описание                                                                                                                                                          |
| ------------------------------------------------------------------ | -------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| [FtmBase::CreateGlobalInterfaceTable](#createglobalinterfacetable) | Создает общую таблицу интерфейса (GIT).                                                                                                                              |
| [FtmBase::DisconnectObject](#disconnectobject)                     | Принудительно освобождает все внешние подключения к объекту. Сервер объекта вызывает реализацию объекта этот метод перед завершением работы системы.                |
| [FtmBase::GetMarshalSizeMax](#getmarshalsizemax)                   | Получите верхнюю границу на число байтов, необходимая для маршалинга заданный указатель интерфейса на указанный объект.                                                |
| [FtmBase::GetUnmarshalClass](#getunmarshalclass)                   | Возвращает идентификатор CLSID, модель COM использует для поиска библиотеки DLL, содержащей код для соответствующего прокси-сервера. COM загружает эту библиотеку DLL для создания неинициализированным экземпляром прокси-сервера. |
| [FtmBase::MarshalInterface](#marshalinterface)                     | Записывает в поток данные, необходимые для инициализации прокси-объект в какой-либо процесс клиента.                                                                          |
| [FtmBase::ReleaseMarshalData](#releasemarshaldata)                 | Уничтожает пакет маршалированного данных.                                                                                                                                    |
| [FtmBase::UnmarshalInterface](#unmarshalinterface)                 | Инициализирует только что созданный прокси-сервер и возвращает указатель интерфейса для этого прокси-сервера.                                                                                    |

### <a name="public-data-members"></a>Открытые члены данных

| name                                | Описание                                       |
| ----------------------------------- | ------------------------------------------------- |
| [FtmBase::marshaller_](#marshaller) | Хранит ссылку на бесплатный упаковщик. |

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`FtmBase`

## <a name="requirements"></a>Требования

**Заголовок:** ftm.h

**Пространство имен:** Microsoft::WRL

## <a name="createglobalinterfacetable"></a>FtmBase::CreateGlobalInterfaceTable

Создает общую таблицу интерфейса (GIT).

```cpp
static HRESULT CreateGlobalInterfaceTable(
   __out IGlobalInterfaceTable **git
);
```

### <a name="parameters"></a>Параметры

*Git*<br/>
После завершения этой операции указатель на общую таблицу интерфейса.

### <a name="return-value"></a>Возвращаемое значение

Значение S_OK, если операция завершилась успешно; в противном случае — значение HRESULT, указывающее на ошибку.

### <a name="remarks"></a>Примечания

Дополнительные сведения см. в разделе `IGlobalInterfaceTable` подразделы `COM Interfaces` подраздела `COM Reference` раздела в библиотеке MSDN.

## <a name="disconnectobject"></a>FtmBase::DisconnectObject

Принудительно освобождает все внешние подключения к объекту. Сервер объекта вызывает реализацию объекта этот метод перед завершением работы системы.

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

## <a name="ftmbase"></a>FtmBase::FtmBase

Инициализирует новый экземпляр класса `FtmBase`.

```cpp
FtmBase();
```

## <a name="getmarshalsizemax"></a>FtmBase::GetMarshalSizeMax

Получите верхнюю границу на число байтов, необходимая для маршалинга заданный указатель интерфейса на указанный объект.

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
Ссылка на идентификатор интерфейса для маршалинга.

*PV*<br/>
Указатель на интерфейс, который должен быть маршалирован; может иметь значение NULL.

*dwDestContext*<br/>
Контекст назначения, где должен быть неупакованный указанный интерфейс.

Укажите одно или несколько значений перечисления MSHCTX.

В настоящее время распаковка может произойти в другое подразделение текущего процесса (MSHCTX_INPROC) или в другом процессе на том же компьютере, что и текущий процесс (MSHCTX_LOCAL).

*pvDestContext*<br/>
Зарезервировано для будущего использования; должен иметь значение NULL.

*mshlflags*<br/>
Флаг, указывающий, является ли данных для маршалинга для передачи обратно в клиентском процессе, типичный случай — диска или записываются на глобальной таблицы, где его можно получить несколькими клиентами. Укажите одно или несколько значений перечисления MSHLFLAGS.

*pSize*<br/>
После завершения этой операции, указатель на верхнюю границу объема данных, записываемых в поток маршалинга.

### <a name="return-value"></a>Возвращаемое значение

Значение S_OK, если выполнение прошло успешно; в противном случае — значение E_FAIL или E_NOINTERFACE.

## <a name="getunmarshalclass"></a>FtmBase::GetUnmarshalClass

Возвращает идентификатор CLSID, модель COM использует для поиска библиотеки DLL, содержащей код для соответствующего прокси-сервера. COM загружает эту библиотеку DLL для создания неинициализированным экземпляром прокси-сервера.

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
Ссылка на идентификатор интерфейса для маршалинга.

*PV*<br/>
Указатель на интерфейс, который должен быть маршалирован; может иметь значение NULL, если вызывающий объект не имеет указатель на нужный интерфейс.

*dwDestContext*<br/>
Контекст назначения, где должен быть неупакованный указанный интерфейс.

Укажите одно или несколько значений перечисления MSHCTX.

Распаковка может произойти либо в другое подразделение текущего процесса (MSHCTX_INPROC) или в другом процессе на том же компьютере, что и текущий процесс (MSHCTX_LOCAL).

*pvDestContext*<br/>
Зарезервировано для будущего использования; должен иметь значение NULL.

*mshlflags*<br/>
После завершения этой операции, указатель на идентификатор CLSID, используемый для создания прокси-сервера в клиентском процессе.

*pCid*

### <a name="return-value"></a>Возвращаемое значение

Значение S_OK, если выполнение прошло успешно; в противном случае значение S_FALSE.

## <a name="marshalinterface"></a>FtmBase::MarshalInterface

Записывает в поток данные, необходимые для инициализации прокси-объект в какой-либо процесс клиента.

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
Указатель на поток, который используется во время маршалинга.

*riid*<br/>
Ссылка на идентификатор интерфейса для маршалинга. Этот интерфейс должен быть производным от `IUnknown` интерфейс.

*PV*<br/>
Указатель на указатель интерфейса, который должен быть маршалирован; может иметь значение NULL, если вызывающий объект не имеет указатель на нужный интерфейс.

*dwDestContext*<br/>
Контекст назначения, где должен быть неупакованный указанный интерфейс.

Укажите одно или несколько значений перечисления MSHCTX.

Распаковка может произойти в другое подразделение текущего процесса (MSHCTX_INPROC) или в другом процессе на том же компьютере, что и текущий процесс (MSHCTX_LOCAL).

*pvDestContext*<br/>
Зарезервировано для будущего использования; должно иметь значение нуль.

*mshlflags*<br/>
Указывает, являются ли данные должны быть маршалированы для передачи обратно в клиентском процессе, типичный случай — диска или записываются на глобальной таблицы, где его можно получить несколькими клиентами.

### <a name="return-value"></a>Возвращаемое значение

Значение S_OK указатель интерфейса был маршалирован успешно.

E_NOINTERFACE указанный интерфейс не поддерживается.

Заполнен STG_E_MEDIUMFULL потока.

Не удалось выполнить операцию E_FAIL.

## <a name="marshaller"></a>FtmBase::marshaller_

Хранит ссылку на бесплатный упаковщик.

```cpp
Microsoft::WRL::ComPtr<IMarshal> marshaller_; ;
```

## <a name="releasemarshaldata"></a>FtmBase::ReleaseMarshalData

Уничтожает пакет маршалированного данных.

```cpp
STDMETHODIMP ReleaseMarshalData(
   __in IStream *pStm
) override;
```

### <a name="parameters"></a>Параметры

*pStm*<br/>
Указатель на поток, содержащий пакет данных будут уничтожены.

### <a name="return-value"></a>Возвращаемое значение

Значение S_OK, если операция завершилась успешно; в противном случае — значение HRESULT, указывающее на ошибку.

## <a name="unmarshalinterface"></a>FtmBase::UnmarshalInterface

Инициализирует только что созданный прокси-сервер и возвращает указатель интерфейса для этого прокси-сервера.

```cpp
STDMETHODIMP UnmarshalInterface(
   __in IStream *pStm,
   __in REFIID riid,
   __deref_out void **ppv
) override;
```

### <a name="parameters"></a>Параметры

*pStm*<br/>
Указатель на поток, из которого должен быть неупакованный указатель на интерфейс.

*riid*<br/>
Ссылка на идентификатор интерфейса необходимо распаковать.

*ppv*<br/>
После завершения операции адрес переменной указателя, получающей указатель интерфейса, запрашиваемый в *riid*. Если операция выполнена успешно, **ppv* содержит запрошенный указатель интерфейса интерфейса необходимо распаковать.

### <a name="return-value"></a>Возвращаемое значение

Значение S_OK, если выполнение прошло успешно; в противном случае — значение E_NOINTERFACE или E_FAIL.
