---
title: грамматика выражения __based | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- based addressing
ms.assetid: a68ff750-c7fa-4c0c-8d5f-2df76e4686c5
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 43e9074de25d8cb914432123478f5f338ff4ba1e
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46103773"
---
# <a name="based-grammar"></a>Грамматика выражения __based

## <a name="microsoft-specific"></a>Блок, относящийся только к системам Microsoft

Базовая адресация полезна, когда требуется точный контроль над сегментом, в котором выделяются объекты (статические и динамические данные).

Единственной формой адресации допустимой в 32-разрядных и 64-разрядных компиляциях «основана на указатель», которая определяет тип, содержащий смещением 32-разрядной или 64-разрядная на 32-разрядная или 64-разрядных базовую или на основе **void**.

## <a name="grammar"></a>Грамматика

*на основе диапазона модификатор*: **__based (***базовому выражению***)** 

*базовому выражению*: *based-variablebased-abstract-declaratorsegment-namesegment-cast*

*на основе переменной*: *идентификатор*

*на основе абстрактный декларатор*: *абстрактный декларатор*

*базового типа*: *имя типа*

**Завершение блока, относящегося только к системам Майкрософт**

## <a name="see-also"></a>См. также

[Относительные указатели](../cpp/based-pointers-cpp.md)