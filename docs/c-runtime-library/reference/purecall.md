---
title: _purecall
ms.date: 11/04/2016
api_name:
- _purecall
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
- ntoskrnl.exe
- ucrtbase.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- purecall
- _purecall
helpviewer_keywords:
- _purecall function
- purecall function
ms.assetid: 56135d9b-3403-4e22-822d-e714523801cc
ms.openlocfilehash: 5d62ec30731ce26c4683afc88474d4bddb63a697
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/12/2019
ms.locfileid: "70950159"
---
# <a name="_purecall"></a>_purecall

Обработчик ошибок вызовов чистой виртуальной функции по умолчанию. При вызове чистой виртуальной функции-члена компилятор создает код для вызова этой функции.

## <a name="syntax"></a>Синтаксис

```C
extern "C" int __cdecl _purecall();
```

## <a name="remarks"></a>Примечания

Функция **_purecall** является детальной реализацией C++ компилятора Майкрософт. Эта функция не предназначена для вызова непосредственно из кода и не содержит объявление открытого заголовка. Она описана здесь, так как это общий экспорт библиотеки времени выполнения C.

Вызов чистой виртуальной функции является ошибкой, так как она не имеет реализации. Компилятор создает код для вызова функции обработчика ошибок **_purecall** при вызове чистой виртуальной функции. По умолчанию **_purecall** завершает программу. Перед завершением работы функция **_purecall** вызывает функцию **_purecall_handler** , если она была задана для процесса. Можно установить собственный обработчик ошибок для вызовов чистых виртуальных функций, который будет перехватывать их в целях отладки или ведения отчетности. Чтобы использовать собственный обработчик ошибок, создайте функцию с сигнатурой **_purecall_handler** , а затем используйте [_set_purecall_handler](get-purecall-handler-set-purecall-handler.md) , чтобы сделать ее текущим обработчиком.

## <a name="requirements"></a>Требования

Функция **_purecall** не имеет объявления заголовка. Определение типа **_purecall_handler** определено в \<stdlib. h >.

## <a name="see-also"></a>См. также

[Алфавитный указатель функций](crt-alphabetical-function-reference.md)<br/>
[_get_purecall_handler, _set_purecall_handler](get-purecall-handler-set-purecall-handler.md)<br/>
