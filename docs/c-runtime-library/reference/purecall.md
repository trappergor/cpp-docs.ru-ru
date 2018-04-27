---
title: _purecall | Документы Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- _purecall
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
- ntoskrnl.exe
- ucrtbase.dll
apitype: DLLExport
f1_keywords:
- purecall
- _purecall
dev_langs:
- C++
helpviewer_keywords:
- _purecall function
- purecall function
ms.assetid: 56135d9b-3403-4e22-822d-e714523801cc
caps.latest.revision: 7
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: bfcd454aa6a4053ff30eef27b9c9c7d3d8bf7b34
ms.sourcegitcommit: ef859ddf5afea903711e36bfd89a72389a12a8d6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/20/2018
---
# <a name="purecall"></a>_purecall

Обработчик ошибок вызовов чистой виртуальной функции по умолчанию. При вызове чистой виртуальной функции-члена компилятор создает код для вызова этой функции.

## <a name="syntax"></a>Синтаксис

```C
extern "C" int __cdecl _purecall();
```

## <a name="remarks"></a>Примечания

**_Purecall** функция является реализации версию компилятора Microsoft Visual C++. Эта функция не предназначена для вызова непосредственно из кода и не содержит объявление открытого заголовка. Она описана здесь, так как это общий экспорт библиотеки времени выполнения C.

Вызов чистой виртуальной функции является ошибкой, так как она не имеет реализации. Компилятор создает код для вызова **_purecall** функция обработчика ошибок, при вызове чистой виртуальной функции. По умолчанию **_purecall** завершает программу. Перед завершением работы, **_purecall** функция вызывает **_purecall_handler** функционировать, если она была настроена для процесса. Можно установить собственный обработчик ошибок для вызовов чистых виртуальных функций, который будет перехватывать их в целях отладки или ведения отчетности. Чтобы использовать собственный обработчик ошибок, создайте функцию, которая имеет **_purecall_handler** подпись, затем с помощью [_set_purecall_handler](get-purecall-handler-set-purecall-handler.md) вносить текущий обработчик.

## <a name="requirements"></a>Требования

**_Purecall** функция не имеет объявления заголовка. **_Purecall_handler** typedef определяется в \<stdlib.h >.

## <a name="see-also"></a>См. также

[Алфавитный указатель функций](crt-alphabetical-function-reference.md)<br/>
[_get_purecall_handler, _set_purecall_handler](get-purecall-handler-set-purecall-handler.md)<br/>
