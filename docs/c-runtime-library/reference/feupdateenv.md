---
title: feupdateenv | Документы Майкрософт
ms.custom: ''
ms.date: 04/05/2018
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp
- devlang-cpp
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- feupdateenv
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
apitype: HeaderDef
f1_keywords:
- feupdateenv
- fenv/feupdateenv
dev_langs:
- C++
helpviewer_keywords:
- feupdateenv function
ms.assetid: 3d170042-dfd5-4e4f-a55f-038cf2296cc9
caps.latest.revision: 3
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 1f731b5a24d952c6e58341662914e185efbac1ab
ms.sourcegitcommit: ef859ddf5afea903711e36bfd89a72389a12a8d6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/20/2018
---
# <a name="feupdateenv"></a>feupdateenv

Сохраняет вызванные в данный момент исключения с плавающей запятой, восстанавливает указанное состояние среды вычислений с плавающей запятой, после чего вызывает сохраненные исключения с плавающей запятой.

## <a name="syntax"></a>Синтаксис

```C
int feupdateenv(
   const fenv_t* penv
);
```

### <a name="parameters"></a>Параметры

*penv*<br/>
Указатель на **fenv_t** объект, содержащий среде с плавающей запятой в виде набора путем вызова [fegetenv](fegetenv1.md) или [feholdexcept](feholdexcept2.md). Кроме того, вы можете указать запускаемую по умолчанию среду вычислений с плавающей запятой с помощью макроса FE_DFL_ENV.

## <a name="return-value"></a>Возвращаемое значение

Если все действия успешно завершены, возвращает 0. В противном случае возвращается ненулевое значение.

## <a name="remarks"></a>Примечания

**Feupdateenv** функция выполняет несколько действий. Сначала она автоматически сохраняет вызванные на данный момент флаги состояний исключения с плавающей запятой. Затем он устанавливает текущую среду с плавающей запятой из значения, хранящегося в **fenv_t** объекта, на который указывает *penv*. Если *penv* не **FE_DFL_ENV** или не указывает на допустимый **fenv_t** объекта, последующее поведение не определено. Наконец **feupdateenv** вызывает локальные исключения с плавающей запятой.

Чтобы использовать эту функцию, необходимо отключить оптимизацию вычислений с плавающей запятой, которая может препятствовать доступу. Для этого следует использовать директиву `#pragma fenv_access(on)` перед вызовом. Дополнительные сведения см. в разделе [fenv_access](../../preprocessor/fenv-access.md).

## <a name="requirements"></a>Требования

|Функция|Заголовок C|Заголовок C++|
|--------------|--------------|------------------|
|**feupdateenv**|\<fenv.h>|\<cfenv>|

Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>См. также

[fegetenv](fegetenv1.md)<br/>
[feclearexcept](feclearexcept1.md)<br/>
[feholdexcept](feholdexcept2.md)<br/>
[fesetexceptflag](fesetexceptflag2.md)<br/>
