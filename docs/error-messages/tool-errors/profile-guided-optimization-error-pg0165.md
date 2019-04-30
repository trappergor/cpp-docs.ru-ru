---
title: Ошибка профильной оптимизации PG0165
ms.date: 11/04/2016
f1_keywords:
- PG0165
helpviewer_keywords:
- PG0165
ms.assetid: e98122e7-ddee-4a2c-96b2-d232e4c65f3e
ms.openlocfilehash: f39bbe6540ebec10cd25c41ac2fe9f2acfca9b13
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62359739"
---
# <a name="profile-guided-optimization-error-pg0165"></a>Ошибка профильной оптимизации PG0165

Чтение «Filename.pgd»: "Версия PGD не поддерживается (несоответствие версии)".

Файлы PGD относятся только к определенному набору инструментов компилятора. Эта ошибка возникает при использовании компилятора, используемое для *Filename*.pgd. Эта ошибка указывает, что набор инструментов компилятора не может использовать данные из *Filename*.pgd для оптимизации текущей программы.

Чтобы устранить эту проблему, повторное создание *Filename*.pgd, используя текущий набор инструментов компилятора.