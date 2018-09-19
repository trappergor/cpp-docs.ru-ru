---
title: Описатель класса хранения register | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- register variables
- register storage class
ms.assetid: 7577bf48-88ec-4191-873c-ef4217a4034e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: e15b6bd4136e2644dbd040ac509b35af772ae4c3
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46028328"
---
# <a name="register-storage-class-specifier"></a>Спецификатор класса хранения register

**Блок, относящийся только к системам Майкрософт**

Компилятор Microsoft C/C++ не учитывает пользовательские запросы на переменные регистра. Но в целях обеспечения переносимости компилятор учитывает всю остальную семантику, связанную с ключевым словом **register**. Например, невозможно применить унарный оператор взятия адреса (**&**) к объекту регистра. Кроме того, ключевое слово **register** невозможно использовать в массивах.

**Завершение блока, относящегося только к системам Майкрософт**

## <a name="see-also"></a>См. также

[Спецификаторы классов хранения для объявлений внутреннего уровня](../c-language/storage-class-specifiers-for-internal-level-declarations.md)