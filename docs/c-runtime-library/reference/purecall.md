---
title: _purecall
ms.date: 11/04/2016
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
helpviewer_keywords:
- _purecall function
- purecall function
ms.assetid: 56135d9b-3403-4e22-822d-e714523801cc
ms.openlocfilehash: df6dde91ccb952e66eb77c841b2b1ace12756b8c
ms.sourcegitcommit: 7d64c5f226f925642a25e07498567df8bebb00d4
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/08/2019
ms.locfileid: "65446625"
---
# <a name="purecall"></a>_purecall

Обработчик ошибок вызовов чистой виртуальной функции по умолчанию. При вызове чистой виртуальной функции-члена компилятор создает код для вызова этой функции.

## <a name="syntax"></a>Синтаксис

```C
extern "C" int __cdecl _purecall();
```

## <a name="remarks"></a>Примечания

**_Purecall** функция является Microsoft — сведения о реализации платформы Microsoft C++ компилятора. Эта функция не предназначена для вызова непосредственно из кода и не содержит объявление открытого заголовка. Она описана здесь, так как это общий экспорт библиотеки времени выполнения C.

Вызов чистой виртуальной функции является ошибкой, так как она не имеет реализации. Компилятор создает код для вызова **_purecall** функции обработки ошибок, при вызове чистой виртуальной функции. По умолчанию **_purecall** завершает программу. Перед завершением работы, **_purecall** функция вызывает **_purecall_handler** работать, если оно было задано для процесса. Можно установить собственный обработчик ошибок для вызовов чистых виртуальных функций, который будет перехватывать их в целях отладки или ведения отчетности. Чтобы использовать собственный обработчик ошибок, создайте функцию, которая имеет **_purecall_handler** подпись, затем с помощью [_set_purecall_handler](get-purecall-handler-set-purecall-handler.md) для упрощения текущего обработчика.

## <a name="requirements"></a>Требования

**_Purecall** функция не имеет объявления заголовка. **_Purecall_handler** typedef определяется в \<stdlib.h >.

## <a name="see-also"></a>См. также

[Алфавитный указатель функций](crt-alphabetical-function-reference.md)<br/>
[_get_purecall_handler, _set_purecall_handler](get-purecall-handler-set-purecall-handler.md)<br/>
