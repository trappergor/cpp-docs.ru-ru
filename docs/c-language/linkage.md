---
title: Компоновка | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- linkage [C++]
- linkage [C++], identifier names and scope
ms.assetid: 986ee549-2d6c-487a-9e3b-a1f643bc5bdc
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: f633d3ebd366c0fa85733f96e5c11e6857a37ae6
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46064325"
---
# <a name="linkage"></a>Компоновка

Имена идентификаторов могут относиться к разным идентификаторам в разных областях. Идентификатор, объявленный в разных областях или в одной и той же области несколько раз, можно настроить таким образом, чтобы он ссылался на один идентификатор или функцию, с помощью процесса компоновки. Компоновка определяет части программы, в которых можно сослаться на идентификатор (его видимость). Существует три типа компоновки: [внутренняя](../c-language/internal-linkage.md), [внешняя](../c-language/external-linkage.md) и [без компоновки](../c-language/no-linkage.md).

## <a name="see-also"></a>См. также

[Использование ключевого слова extern для задания компоновки](../cpp/using-extern-to-specify-linkage.md)