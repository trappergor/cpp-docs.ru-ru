---
title: Прагма auto_inline
ms.date: 08/29/2019
f1_keywords:
- auto_inline_CPP
- vc-pragma.auto_inline
helpviewer_keywords:
- pragmas, auto_inline
- auto_inline pragma
ms.assetid: f7624cd1-be76-429a-881c-65c9040acf43
ms.openlocfilehash: 59cda8cb73196215318c9570a5c067786284afaa
ms.sourcegitcommit: 6e1c1822e7bcf3d2ef23eb8fac6465f88743facf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/03/2019
ms.locfileid: "70216312"
---
# <a name="auto_inline-pragma"></a>Прагма auto_inline

Исключает все функции, определенные в диапазоне, где значение **Off** определяется как кандидаты для автоматического встраивания.

## <a name="syntax"></a>Синтаксис

> **#pragma auto_inline (** [{ **On** | **Off** }] **)**

## <a name="remarks"></a>Примечания

Чтобы использовать директиву pragma **auto_inline** , поместите ее до и сразу после, а не внутри, определение функции. Директива pragma вступает в силу сразу после того, как будет отображено первое определение функции после директивы pragma.

## <a name="see-also"></a>См. также

[Директивы pragma и ключевое слово __pragma](../preprocessor/pragma-directives-and-the-pragma-keyword.md)
