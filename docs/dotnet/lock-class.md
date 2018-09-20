---
title: Класс LOCK | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- msclr::lock
- msclr.lock
- lock
dev_langs:
- C++
helpviewer_keywords:
- lock class
ms.assetid: 5123edd9-6aed-497d-9a0b-f4b6d6c0d666
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 7ef0887ca3eec7510717aab21ba4c6c7aba98d25
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46380299"
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