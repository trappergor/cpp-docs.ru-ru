---
title: jitintrinsic
ms.date: 11/04/2016
f1_keywords:
- jitintrinsic
- jitintrinsic_cpp
helpviewer_keywords:
- __declspec keyword [C++], jitintrinsic
- jitintrinsic __declspec modifier
ms.assetid: 23dbe416-7ef6-442b-b16d-9a81aab04fa6
ms.openlocfilehash: 9e726413f0bbfbd9d6affa348777c995c51283a5
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62245522"
---
# <a name="jitintrinsic"></a>jitintrinsic

Помечает функцию как значимую для 64-разрядной среды CLR. Этот модификатор используется с определенными функциями в библиотеках Microsoft.

## <a name="syntax"></a>Синтаксис

```
__declspec(jitintrinsic)
```

## <a name="remarks"></a>Примечания

**jitintrinsic** добавляет MODOPT (<xref:System.Runtime.CompilerServices.IsJitIntrinsic>) к сигнатуре функции.

Пользователям не рекомендуется применять этот **__declspec** модификатор, как непредвиденные результаты могут возникать.

## <a name="see-also"></a>См. также

[__declspec](../cpp/declspec.md)<br/>
[Ключевые слова](../cpp/keywords-cpp.md)