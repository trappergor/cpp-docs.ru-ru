---
title: Макросы команд и параметров
description: Описание предопределенных макросов NMAKE для средств сборки и их параметров.
ms.date: 11/20/2019
helpviewer_keywords:
- options macros
- command macros in NMAKE
- macros, options macros
- macros, command macros
ms.assetid: 50dff03c-0dc3-4a8a-9a17-57e0e4ea9bac
no-loc:
- AS
- AFLAGS
- CC
- CFLAGS
- CPP
- CPPFLAGS
- CXX
- CXXFLAGS
- RC
- RFLAGS
- ias
- ml
- ml64
- cl
- rc
ms.openlocfilehash: d5c4477fd97e2a6c48dbac4d0ce83f7fd5f12ad6
ms.sourcegitcommit: 069e3833bd821e7d64f5c98d0ea41fc0c5d22e53
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2019
ms.locfileid: "74303178"
---
# <a name="command-macros-and-options-macros"></a>Макросы команд и параметров

Макросы команд предопределены для продуктов Майкрософт. Макросы параметров представляют параметры для этих продуктов и не определены по умолчанию. Оба используются в стандартных правилах вывода и могут использоваться в блоках описания или в пользовательских правилах вывода. Командные макросы могут быть переопределены для представления части или всей командной строки, включая параметры. Макросы параметров создают пустую строку, если не задано значение Left.

|Продукт Майкрософт|Командный макрос|Определение|Макрос параметров|
|-----------------------|-------------------|----------------|-------------------|
|Ассемблер макроса|**AS**|ml, ias или ml64|**AFLAGS**|
|Компилятор C|**CC**|cl|**CFLAGS**|
|Компилятор C++|**CPP**|cl|**CPPFLAGS**|
|Компилятор C++|**CXX**|cl|**CXXFLAGS**|
|компилятор ресурсов|**RC**|RC|**RFLAGS**|

## <a name="see-also"></a>См. также:

[Специальные макросы NMAKE](special-nmake-macros.md)
