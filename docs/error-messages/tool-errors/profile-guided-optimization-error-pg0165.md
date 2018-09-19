---
title: Профильной оптимизации PG0165 ошибка | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- PG0165
dev_langs:
- C++
helpviewer_keywords:
- PG0165
ms.assetid: e98122e7-ddee-4a2c-96b2-d232e4c65f3e
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 332751a123bf7d6414c40b79870b5edf27a3d8a7
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46084215"
---
# <a name="profile-guided-optimization-error-pg0165"></a>Ошибка профильной оптимизации PG0165

Чтение «Filename.pgd»: "версия PGD не поддерживается (несоответствие версии)".

Файлы PGD относятся только к определенному набору инструментов компилятора. Эта ошибка возникает при использовании компилятора, используемое для *Filename*.pgd. Эта ошибка указывает, что набор инструментов компилятора не может использовать данные из *Filename*.pgd для оптимизации текущей программы.

Чтобы устранить эту проблему, повторное создание *Filename*.pgd, используя текущий набор инструментов компилятора.