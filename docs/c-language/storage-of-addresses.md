---
title: Хранение адресов
ms.date: 11/04/2016
helpviewer_keywords:
- storage [C++], addresses
- addresses [C++], storage of
ms.assetid: 423b2402-b847-4788-ad70-943b7c9c5c8b
ms.openlocfilehash: 2a0e218d4d34fa1482986ecccd7da8adba38086b
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50539377"
---
# <a name="storage-of-addresses"></a>Хранение адресов

Объем хранилища, необходимый для адреса, и значение адреса зависят от реализации компилятора. Одинаковая длина указателей на разные типы не гарантируется. Поэтому значение **sizeof(char \*)** необязательно равно значению **sizeof(int \*)**.

**Блок, относящийся только к системам Microsoft**

Для компилятора Microsoft C значение **sizeof(char \*)** равно значению **sizeof(int \*)**.

**Завершение блока, относящегося только к системам Майкрософт**

## <a name="see-also"></a>См. также

[Объявления указателей](../c-language/pointer-declarations.md)