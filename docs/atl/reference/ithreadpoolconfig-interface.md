---
title: Интерфейс IThreadPoolConfig
ms.date: 11/04/2016
f1_keywords:
- IThreadPoolConfig
- ATLUTIL/ATL::IThreadPoolConfig
- ATLUTIL/ATL::GetSize
- ATLUTIL/ATL::GetTimeout
- ATLUTIL/ATL::SetSize
- ATLUTIL/ATL::SetTimeout
helpviewer_keywords:
- IThreadPoolConfig interface
ms.assetid: 69e642bf-6925-46e6-9a37-cce52231b1cc
ms.openlocfilehash: e4b90534fa89ef2aeffe4cd682d92efc16452487
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81326354"
---
# <a name="ithreadpoolconfig-interface"></a>Интерфейс IThreadPoolConfig

Этот интерфейс предоставляет методы настройки пула потоков.

> [!IMPORTANT]
> Этот класс и его члены не могут быть использованы в приложениях, выполняемых в Windows Runtime.

## <a name="syntax"></a>Синтаксис

```
__interface
    __declspec(uuid("B1F64757-6E88-4fa2-8886-7848B0D7E660")) IThreadPoolConfig : public IUnknown
```

## <a name="members"></a>Участники

### <a name="methods"></a>Методы

|||
|-|-|
|[GetSize](#getsize)|Вызовите этот метод, чтобы получить количество потоков в пуле.|
|[GetTimeout](#gettimeout)|Вызовите этот метод, чтобы получить максимальное время в миллисекундах, что пул потоков будет ждать потока, чтобы выключить.|
|[Setsize](#setsize)|Вызовите этот метод, чтобы установить количество потоков в пуле.|
|[Settimeout](#settimeout)|Вызовите этот метод, чтобы установить максимальное время в миллисекундах, что пул потоков будет ждать потока, чтобы выключить.|

## <a name="remarks"></a>Remarks

Этот интерфейс реализован [CThreadPool](../../atl/reference/cthreadpool-class.md).

## <a name="requirements"></a>Требования

**Заголовок:** atlutil.h

## <a name="ithreadpoolconfiggetsize"></a><a name="getsize"></a>IThreadPoolConfig::GetSize

Вызовите этот метод, чтобы получить количество потоков в пуле.

```
STDMETHOD(GetSize)(int* pnNumThreads);
```

### <a name="parameters"></a>Параметры

*pnNumThreads*<br/>
(ваут) Адрес переменной, которая, по успеху, получает количество потоков в пуле.

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK на успех, или ошибка HRESULT на отказ.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATL_Utilities#134](../../atl/codesnippet/cpp/ithreadpoolconfig-interface_1.cpp)]

## <a name="ithreadpoolconfiggettimeout"></a><a name="gettimeout"></a>IThreadPoolConfig::GetTimeout

Вызовите этот метод, чтобы получить максимальное время в миллисекундах, что пул потоков будет ждать потока, чтобы выключить.

```
STDMETHOD(GetTimeout)(DWORD* pdwMaxWait);
```

### <a name="parameters"></a>Параметры

*pdwMaxWait*<br/>
(ваут) Адрес переменной, которая, по успеху, получает максимальное время в миллисекундах, что пул потоков будет ждать потока, чтобы выключить.

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK на успех, или ошибка HRESULT на отказ.

### <a name="example"></a>Пример

Смотрите [IThreadPoolConfig::GetSize](#getsize).

## <a name="ithreadpoolconfigsetsize"></a><a name="setsize"></a>IThreadPoolConfig::SetSize

Вызовите этот метод, чтобы установить количество потоков в пуле.

```
STDMETHOD(SetSize)int nNumThreads);
```

### <a name="parameters"></a>Параметры

*nNumThreads*<br/>
Запрошенное количество потоков в пуле.

Если *nNumThreads* отрицательный, его абсолютное значение будет умножаться на количество процессоров в машине, чтобы получить общее количество потоков.

Если *nNumThreads* равен нулю, ATLS_DEFAULT_THREADSPERPROC будет умножаться на количество процессоров в машине, чтобы получить общее количество потоков.

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK на успех, или ошибка HRESULT на отказ.

### <a name="example"></a>Пример

Смотрите [IThreadPoolConfig::GetSize](#getsize).

## <a name="ithreadpoolconfigsettimeout"></a><a name="settimeout"></a>IThreadPoolConfig::SetTimeout

Вызовите этот метод, чтобы установить максимальное время в миллисекундах, что пул потоков будет ждать потока, чтобы выключить.

```
STDMETHOD(SetTimeout)(DWORD dwMaxWait);
```

### <a name="parameters"></a>Параметры

*dwMaxWait*<br/>
Запрошенное максимальное время в миллисекундах, что пул потоков будет ждать потока, чтобы выключить.

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK на успех, или ошибка HRESULT на отказ.

### <a name="example"></a>Пример

Смотрите [IThreadPoolConfig::GetSize](#getsize).

## <a name="see-also"></a>См. также раздел

[Классы](../../atl/reference/atl-classes.md)<br/>
[Класс CThreadPool](../../atl/reference/cthreadpool-class.md)
