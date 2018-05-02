---
title: setjmp | Документы Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- setjmp
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
- setjmp
dev_langs:
- C++
helpviewer_keywords:
- programs [C++], saving states
- current state
- setjmp function
ms.assetid: 684a8b27-e8eb-455b-b4a8-733ca1cbd7d2
caps.latest.revision: 12
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: dc01f80aa4521ff3588cca14ceabbf5447338cca
ms.sourcegitcommit: ef859ddf5afea903711e36bfd89a72389a12a8d6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/20/2018
---
# <a name="setjmp"></a>setjmp

Сохраняет текущее состояние программы.

## <a name="syntax"></a>Синтаксис

```C
int setjmp(
   jmp_buf env
);
```

### <a name="parameters"></a>Параметры

*env*<br/>
Переменная, в которой хранится среда.

## <a name="return-value"></a>Возвращаемое значение

Возвращает 0 после сохранения среды стека. Если **setjmp** возвращается в результате **longjmp** вызвать, она возвращает **значение** аргумент **longjmp**, или если **значение**  аргумент **longjmp** равно 0, **setjmp** возвращает 1. Ошибка не возвращается.

## <a name="remarks"></a>Примечания

**Setjmp** функция сохраняет среду стека, который можно впоследствии восстановить, используя **longjmp**. При совместном использовании **setjmp** и **longjmp** предоставляют способ выполнения нелокального **goto**. Обычно они используются для передачи управления выполнением в код обработки ошибок или восстановления в вызванной ранее подпрограмме без использования обычных соглашений вызова или возврата.

Вызов **setjmp** сохраняет текущую среду стека в *env*. В последующем вызове **longjmp** восстанавливает сохраненную среду и возвращает управление в точку сразу за соответствующим **setjmp** вызова. Все переменные (за исключением регистровых переменных) доступны для получившей управление подпрограммы, содержат значения, они имели при **longjmp** был вызван.

Невозможно использовать **setjmp** для перехода из машинного кода в управляемый.

**Примечание** **setjmp** и **longjmp** не поддерживают семантику объекта C++. В программах на C++ используйте механизм обработки исключений C++.

Дополнительные сведения см. в разделе [Использование setjmp и longjmp](../../cpp/using-setjmp-longjmp.md).

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**setjmp**|\<setjmp.h>|

Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Пример

См. пример для [_fpreset](fpreset.md).

## <a name="see-also"></a>См. также

[Управление процессами и средой](../../c-runtime-library/process-and-environment-control.md)<br/>
[longjmp](longjmp.md)<br/>
[_setjmp3](../../c-runtime-library/setjmp3.md)<br/>
