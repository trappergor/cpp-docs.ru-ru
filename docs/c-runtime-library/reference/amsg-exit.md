---
title: _amsg_exit
ms.date: 11/04/2016
api_name:
- _amsg_exit
api_location:
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
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _amsg_exit
helpviewer_keywords:
- _amsg_exit
ms.assetid: 146d4faf-d763-43a4-b264-12711196456b
ms.openlocfilehash: 2d577bfcf0584ef982ab43ff98674d0cfadd14ba
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/12/2019
ms.locfileid: "70939699"
---
# <a name="_amsg_exit"></a>_amsg_exit

Создает указанное сообщение об ошибке времени выполнения, затем завершает приложение с кодом ошибки 255.

## <a name="syntax"></a>Синтаксис

```cpp
void _amsg_exit ( int rterrnum );
```

### <a name="parameters"></a>Параметры

*ртеррнум*<br/>
Идентификационный номер определяемого системой сообщения об ошибке времени выполнения.

## <a name="remarks"></a>Примечания

Эта функция посылает сообщение об ошибке времени выполнения в поток **stderr** для консольных приложений или отображает сообщение в окне сообщения для приложений Windows. В режиме отладки перед выходом можно вызвать отладчик.

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|_amsg_exit|internal.h|