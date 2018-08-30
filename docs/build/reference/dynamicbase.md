---
title: -DYNAMICBASE | Документация Майкрософт
ms.custom: ''
ms.date: 06/12/2018
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /dynamicbase
dev_langs:
- C++
helpviewer_keywords:
- -DYNAMICBASE editbin option
- DYNAMICBASE editbin option
- /DYNAMICBASE editbin option
ms.assetid: edb3df90-7b07-42fb-a94a-f5a4c1d325d6
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 255123157da3f802eafaf26206598d54fea02335
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/29/2018
ms.locfileid: "43223443"
---
# <a name="dynamicbase"></a>/DYNAMICBASE

Указывает, следует ли создавать исполняемый образ, который может быть случайным образом переместить во время загрузки с помощью функции Windows, впервые появившаяся в Windows Vista адрес макета пространства randomization (ASLR).

## <a name="syntax"></a>Синтаксис

> **/ DYNAMICBASE**[**: НЕТ**]

## <a name="remarks"></a>Примечания

**/DYNAMICBASE** параметр изменяет заголовок *исполняемый образ*, файл .dll или .exe, чтобы указать, использует ли приложение следует случайным образом переместить во время загрузки и включает виртуальный адрес случайный выбор срока выделения, что влияет на расположение виртуальной памяти кучи, стеки и выделения памяти для операционной системы. **/DYNAMICBASE** параметр применяется к 32-разрядных и 64-разрядные образы. ASLR поддерживается в Windows Vista и более поздних операционных системах. Параметр обрабатывается в более ранних операционных систем.

По умолчанию **/DYNAMICBASE** включен. Чтобы отключить этот параметр, используйте **/DYNAMICBASE:NO**. **/DYNAMICBASE** параметр является обязательным для [/highentropyva](highentropyva-support-64-bit-aslr.md) параметр вступил в силу.

## <a name="see-also"></a>См. также

- [Параметры EDITBIN](../../build/reference/editbin-options.md)
- [Способы защиты программного обеспечения для независимых поставщиков программного обеспечения Windows](https://msdn.microsoft.com/library/bb430720.aspx)