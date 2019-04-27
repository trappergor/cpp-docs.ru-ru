---
title: .CODE
ms.date: 08/30/2018
f1_keywords:
- .CODE
helpviewer_keywords:
- .CODE directive
ms.assetid: 2b8c882c-c0d2-4fa3-8335-e6b12717a4f4
ms.openlocfilehash: 65d336d2829c97fdf21e6f4b0fcb3063cc7776ee
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62204378"
---
# <a name="code"></a>.CODE

При использовании с [. МОДЕЛЬ](../../assembler/masm/dot-model.md), указывает на начало сегмент кода.

## <a name="syntax"></a>Синтаксис

> . КОД [[имя]]

#### <a name="parameters"></a>Параметры

|Параметр|Описание|
|---------------|-----------------|
|`name`|Необязательный параметр, который задает имя сегмента кода. Имя по умолчанию — _TEXT compact мало места, "мелкая", и плоский [моделей](../../assembler/masm/dot-model.md). Имя по умолчанию — *modulename*_TEXT для других моделей.|

## <a name="see-also"></a>См. также

[Справочник по директивам](../../assembler/masm/directives-reference.md)<br/>
[.DATA](../../assembler/masm/dot-data.md)<br/>