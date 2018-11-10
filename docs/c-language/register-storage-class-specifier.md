---
title: Спецификатор класса хранения register
ms.date: 11/04/2016
helpviewer_keywords:
- register variables
- register storage class
ms.assetid: 7577bf48-88ec-4191-873c-ef4217a4034e
ms.openlocfilehash: 339a96e33e186ddcc0615f89ff68a7f87b0bfdc7
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50668654"
---
# <a name="register-storage-class-specifier"></a>Спецификатор класса хранения register

**Блок, относящийся только к системам Майкрософт**

Компилятор Microsoft C/C++ не учитывает пользовательские запросы на переменные регистра. Но в целях обеспечения переносимости компилятор учитывает всю остальную семантику, связанную с ключевым словом **register**. Например, невозможно применить унарный оператор взятия адреса (**&**) к объекту регистра. Кроме того, ключевое слово **register** невозможно использовать в массивах.

**Завершение блока, относящегося только к системам Майкрософт**

## <a name="see-also"></a>См. также

[Спецификаторы классов хранения для объявлений внутреннего уровня](../c-language/storage-class-specifiers-for-internal-level-declarations.md)