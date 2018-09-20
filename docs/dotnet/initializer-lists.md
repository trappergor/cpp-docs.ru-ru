---
title: Списки инициализаторов | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- initializer lists
ms.assetid: b3e53442-9809-4105-9226-ae845bd20cae
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 981f2737d370dc25ca4e7dc6c20947b3867a0c65
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46394612"
---
# <a name="initializer-lists"></a>Списки инициализатора

Списки инициализатора в конструкторах теперь вызываются до конструктор базового класса.

## <a name="remarks"></a>Примечания

До Visual C++ 2005 конструктор базового класса был вызван перед список инициализаторов, при компиляции с помощью управляемых расширений для C++. Теперь при компиляции с параметром **/CLR**, сначала вызывается список инициализаторов.

## <a name="see-also"></a>См. также

[Общие изменения в языке (C++/CLI)](../dotnet/general-language-changes-cpp-cli.md)