---
title: Неустранимая ошибка CVTRES CVT1100 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- CVT1100
dev_langs:
- C++
helpviewer_keywords:
- CVT1100
ms.assetid: 886e88dd-5818-4b5f-84f2-d2a3d75f0aaf
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 18a5508301c54637fb34a751c8f1c4e307e47d50
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46068966"
---
# <a name="cvtres-fatal-error-cvt1100"></a>Неустранимая ошибка CVTRES CVT1100

дублировать ресурсов, тип: тип, имя: имя, язык: язык, флаги: флаги, размер: размер

Данный ресурс был указан более одного раза.

Эта ошибка может возникнуть, если компоновщик создает библиотеку типов, и вы не указали [/TLBID](../../build/reference/tlbid-specify-resource-id-for-typelib.md) и ресурсов в проекте уже использует 1. В этом случае укажите /TLBID и укажите другой номер до 65535.