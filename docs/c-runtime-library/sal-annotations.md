---
title: Примечания SAL | Документы Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: conceptual
dev_langs:
- C++
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
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 2eb935285c8c90c238baf59cd11a1232fa33d895
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="sal-annotations"></a>Примечания SAL
При просмотре библиотечных заголовочных файлов вы можете обратить внимание на некоторые непривычные заметки, например `_In_z` и `_Out_z_cap_(_Size)`. Это примеры языка заметок для исходного кода Microsoft (SAL), который предоставляет набор заметок, позволяющих описывать, как функция использует свои параметры, например, предположения о параметрах и гарантии при завершении. Заметки определяются в файле заголовка \<sal.h>.  
  
 Дополнительные сведения об использовании аннотаций SAL в Visual Studio см. в разделе [Использование аннотаций SAL для сокращения количества дефектов в коде C/C++](/visualstudio/code-quality/using-sal-annotations-to-reduce-c-cpp-code-defects).  
  
## <a name="see-also"></a>См. также  
 [Функции библиотеки CRT](../c-runtime-library/crt-library-features.md)