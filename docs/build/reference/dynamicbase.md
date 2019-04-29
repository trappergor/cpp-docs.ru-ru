---
title: /DYNAMICBASE
ms.date: 06/12/2018
f1_keywords:
- /dynamicbase
helpviewer_keywords:
- -DYNAMICBASE editbin option
- DYNAMICBASE editbin option
- /DYNAMICBASE editbin option
ms.assetid: edb3df90-7b07-42fb-a94a-f5a4c1d325d6
ms.openlocfilehash: 13987b4ba9c25db0f5417da562ff86f4230937d7
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62271831"
---
# <a name="dynamicbase"></a>/DYNAMICBASE

Указывает, следует ли создавать исполняемый образ, который может быть случайным образом переместить во время загрузки с помощью функции Windows, впервые появившаяся в Windows Vista адрес макета пространства randomization (ASLR).

## <a name="syntax"></a>Синтаксис

> **/DYNAMICBASE**[**:NO**]

## <a name="remarks"></a>Примечания

**/DYNAMICBASE** параметр изменяет заголовок *исполняемый образ*, файл .dll или .exe, чтобы указать, использует ли приложение следует случайным образом переместить во время загрузки и включает виртуальный адрес случайный выбор срока выделения, что влияет на расположение виртуальной памяти кучи, стеки и выделения памяти для операционной системы. **/DYNAMICBASE** параметр применяется к 32-разрядных и 64-разрядные образы. ASLR поддерживается в Windows Vista и более поздних операционных системах. Параметр обрабатывается в более ранних операционных систем.

По умолчанию **/DYNAMICBASE** включен. Чтобы отключить этот параметр, используйте **/DYNAMICBASE:NO**. **/DYNAMICBASE** параметр является обязательным для [/highentropyva](highentropyva-support-64-bit-aslr.md) параметр вступил в силу.

## <a name="see-also"></a>См. также

- [Параметры EDITBIN](editbin-options.md)
- [Способы защиты программного обеспечения для независимых поставщиков программного обеспечения Windows](https://msdn.microsoft.com/library/bb430720.aspx)