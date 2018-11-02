---
title: _amsg_exit
ms.date: 11/04/2016
apiname:
- _amsg_exit
apilocation:
- msvcrt.dll
- msvcr80.dll
- msvcr90.dll
- msvcr100.dll
- msvcr100_clr0400.dll
- msvcr110.dll
- msvcr110_clr0400.dll
- msvcr120.dll
- msvcr120_clr0400.dll
- ucrtbase.dll
apitype: DLLExport
f1_keywords:
- _amsg_exit
helpviewer_keywords:
- _amsg_exit
ms.assetid: 146d4faf-d763-43a4-b264-12711196456b
ms.openlocfilehash: 87cd08a6c60a1e29b8a8e15edbfdd69d338d875d
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50534034"
---
# <a name="amsgexit"></a>_amsg_exit

Создает указанное сообщение об ошибке времени выполнения, затем завершает приложение с кодом ошибки 255.

## <a name="syntax"></a>Синтаксис

```cpp
void _amsg_exit ( int rterrnum );
```

### <a name="parameters"></a>Параметры

*rterrnum*<br/>
Идентификационный номер определяемого системой сообщения об ошибке времени выполнения.

## <a name="remarks"></a>Примечания

Эта функция посылает сообщение об ошибке времени выполнения в поток **stderr** для консольных приложений или отображает сообщение в окне сообщения для приложений Windows. В режиме отладки перед выходом можно вызвать отладчик.

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|_amsg_exit|internal.h|