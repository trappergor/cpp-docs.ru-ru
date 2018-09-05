---
title: . КОД | Документация Майкрософт
ms.custom: ''
ms.date: 08/30/2018
ms.technology:
- cpp-masm
ms.topic: reference
f1_keywords:
- .CODE
dev_langs:
- C++
helpviewer_keywords:
- .CODE directive
ms.assetid: 2b8c882c-c0d2-4fa3-8335-e6b12717a4f4
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: ff2d66cfc79e84c8c4c7cf92e117c9ac8c84a555
ms.sourcegitcommit: a7046aac86f1c83faba1088c80698474e25fe7c3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/04/2018
ms.locfileid: "43682491"
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