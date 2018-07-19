---
title: Ошибка компилятора C2865 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2865
dev_langs:
- C++
helpviewer_keywords:
- C2865
ms.assetid: 973eb6a0-c99a-4d25-b3e5-fe0539794d77
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 70b2c6c831fde18f9054e139a120d834a75b6950
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33246220"
---
# <a name="compiler-error-c2865"></a>Ошибка компилятора C2865
«функция»: недопустимое сравнение для дескриптора_или_указателя  
  
 Вы можете сравнить ссылки на [классы и структуры](../../windows/classes-and-structs-cpp-component-extensions.md) или управляемых типов ссылку только на равенство для просмотра, если они ссылаются на один и тот же объект (==) или на разные объекты (! =).  
  
 Невозможно сравнить их для упорядочивания, так как среда выполнения .NET может переместить управляемых объектов в любое время изменить результат теста.