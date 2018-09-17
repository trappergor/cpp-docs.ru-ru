---
title: Varargs | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: aac0c54b-0a2d-4a22-b1de-ee41381a3eb1
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 8305eaddf87a2e67b797bedff1944dbcbbbdbd41
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/17/2018
ms.locfileid: "45713652"
---
# <a name="varargs"></a>Функции с переменным количеством аргументов (Varargs)

Если параметры передаются через varargs (например, кнопку с многоточием аргументов), по сути обычная передача параметра применяется, включая вытеснение пятого и последующих аргументов. Отвечает за снова вызываемого объекта дамп аргументов, которые получают свой адрес. Для значений с плавающей запятой только как целое число, так и в регистре с плавающей запятой будет содержать значение с плавающей запятой в случае, если вызываемый объект ожидает значение в целочисленные регистры.

## <a name="see-also"></a>См. также

[Соглашение о вызовах](../build/calling-convention.md)