---
title: LOCAL (MASM)
ms.date: 08/30/2018
f1_keywords:
- Local
helpviewer_keywords:
- LOCAL directive
ms.assetid: 76147e2d-23ca-4f1e-8817-81428becd113
ms.openlocfilehash: c3a04f68b7fd17b2b6459c219a98fd99ec2d62d4
ms.sourcegitcommit: 9ee5df398bfd30a42739632de3e165874cb675c3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74397256"
---
# <a name="local-masm"></a>LOCAL (MASM)

В первой директиве в макросе **Local** определяет метки, уникальные для каждого экземпляра макроса.

## <a name="syntax"></a>Синтаксис

> **Local** *LocalName* ⟦, *LocalName* ... ⟧
>
> **Локальная** *Метка* ⟦ __\[__ *число* __]__ ⟧ __⟦:__ *Type*⟧ ⟦ __,__ *Label* ⟦ __\[__ *Count* __]__ ⟧ ⟦*Type*⟧... ⟧

## <a name="remarks"></a>Примечания

Во второй директиве в определении процедуры (**proc**) **Local** создает переменные на основе стека, которые существуют в течение данной процедуры. *Метка* может быть простой переменной или массивом, содержащим элементы *Count* .

## <a name="see-also"></a>См. также:

[Справочник по директивам](directives-reference.md)
