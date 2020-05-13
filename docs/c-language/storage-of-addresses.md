---
title: Хранение адресов
ms.date: 11/04/2016
helpviewer_keywords:
- storage [C++], addresses
- addresses [C++], storage of
ms.assetid: 423b2402-b847-4788-ad70-943b7c9c5c8b
ms.openlocfilehash: 47b09ab6cd0b2045206daaee4badad32858ff934
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62336196"
---
# <a name="storage-of-addresses"></a>Хранение адресов

Объем хранилища, необходимый для адреса, и значение адреса зависят от реализации компилятора. Одинаковая длина указателей на разные типы не гарантируется. Поэтому значение **sizeof(char \*)** необязательно равно значению **sizeof(int \*)** .

**Блок, относящийся только к системам Microsoft**

Для компилятора Microsoft C значение **sizeof(char \*)** равно значению **sizeof(int \*)** .

**Завершение блока, относящегося только к системам Майкрософт**

## <a name="see-also"></a>См. также

[Объявления указателей](../c-language/pointer-declarations.md)
