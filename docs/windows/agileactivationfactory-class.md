---
title: Класс AgileActivationFactory | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::AgileActivationFactory
dev_langs:
- C++
ms.assetid: fab98f32-bb93-4c0f-badb-49fbddb194b0
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 2d6b2ff0b9b23e8e3a540cf7bbcd6ae55ebab13d
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46435380"
---
# <a name="agileactivationfactory-class"></a>Класс AgileActivationFactory

Представляет фабрику активации подразделения с поддержкой, который реализует [FtmBase](../windows/ftmbase-class.md).
  
## <a name="syntax"></a>Синтаксис
  
```cpp
template <
   typename I0 = Details::Nil,
   typename I1 = Details::Nil,
   typename I2 = Details::Nil,
FactoryCacheFlags cacheFlagValue = FactoryCacheDefault>
class AgileActivationFactory :
   public ActivationFactory<Implements<FtmBase, I0>, I1, I2, cacheFlagValue>{};
```
  
## <a name="requirements"></a>Требования

**Заголовок:** module.h
  
**Пространство имен:** Microsoft::WRL
  
## <a name="see-also"></a>См. также

[Пространство имен Microsoft::WRL](../windows/microsoft-wrl-namespace.md)<br/>
[Класс ActivationFactory](../windows/activationfactory-class.md)