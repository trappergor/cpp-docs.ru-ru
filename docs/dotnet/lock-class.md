---
title: Класс lock
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- msclr::lock
- msclr.lock
- lock
helpviewer_keywords:
- lock class
ms.assetid: 5123edd9-6aed-497d-9a0b-f4b6d6c0d666
ms.openlocfilehash: 8876810b15a7d2736f2c8ab0ca1f4c6011918a5f
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50547138"
---
# <a name="lock-class"></a>Класс lock

Этот класс позволяет автоматизировать блокировка для синхронизации доступа к объекту из нескольких потоков.  При создании получит блокировку и при уничтожении его выпуски блокировки.

## <a name="syntax"></a>Синтаксис

```
ref class lock;
```

## <a name="remarks"></a>Примечания

`lock` доступен только для объектов среды CLR и может использоваться только в коде среды CLR.

На внутреннем уровне класс использует блокировки <xref:System.Threading.Monitor> для синхронизации доступа. См. в этом разделе для получения дополнительных сведений о синхронизации.

## <a name="requirements"></a>Требования

**Файл заголовка** \<msclr\lock.h >

**Пространство имен** msclr

## <a name="see-also"></a>См. также

[lock](../dotnet/lock.md)<br/>
[Члены lock](../dotnet/lock-members.md)