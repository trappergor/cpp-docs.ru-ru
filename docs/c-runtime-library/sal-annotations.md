---
title: Примечания SAL
description: Краткое описание языка аннотирования Microsoft Source-Code (SAL).
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- __z annotation
- ref annotation
- _opt annotation
- __checkreturn annotatioin
- __deref_opt annotation
- deref_opt annotation
- __deref annotation
- __in annotation
- annotations [C++]
- z annotation
- _inout annotation
- __ref annotation
- full annotation
- _in annotation
- _ref annotation
- __out annotation
- _ecount annotation
- SAL annotations
- __opt annotation
- inout annotation
- in annotation
- _CA_SHOULD_CHECK_RETURN
- __bcount annotation
- _full annotation
- _bcount annotation
- deref annotation
- part annotation
- _out annotation
- __nz annotation
- __part annotation
- opt annotation
- __full annotation
- _nz annotation
- _z annotation
- out annotation
- __ecount annotation
- __inout annotation
- SAL annotations, _CA_SHOULD_CHECK_RETURN
- _deref_opt annotation
- _deref annotation
- nz annotation
- _part annotation
- ecount annotation
- bcount annotation
ms.assetid: 81893638-010c-41a0-9cb3-666fe360f3e0
ms.openlocfilehash: 727c81ae1b141346bb47ff92b6af76d5c45aa106
ms.sourcegitcommit: 9451db8480992017c46f9d2df23fb17b503bbe74
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/30/2020
ms.locfileid: "91590268"
---
# <a name="sal-annotations"></a>Примечания SAL

При просмотре библиотечных заголовочных файлов вы можете обратить внимание на некоторые непривычные заметки, например `_In_z` и `_Out_z_cap_(_Size)`. Это примеры языка заметок для исходного кода Microsoft (SAL), который предоставляет набор заметок, позволяющих описывать, как функция использует свои параметры, например, предположения о параметрах и гарантии при завершении. \<sal.h>Заметки определяются в файле заголовка.

Дополнительные сведения об использовании аннотаций SAL в Visual Studio см. в разделе [Использование аннотаций SAL для сокращения количества дефектов в коде C/C++](../code-quality/using-sal-annotations-to-reduce-c-cpp-code-defects.md).

## <a name="see-also"></a>См. также

[Возможности библиотеки CRT](../c-runtime-library/crt-library-features.md)
