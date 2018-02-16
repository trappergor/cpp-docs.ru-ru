---
title: "Интерфейс Platform::IBoxArray | Документы Microsoft"
ms.custom: 
ms.date: 12/30/2016
ms.technology: cpp-windows
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- VCCORLIB/Namespace not found::Platform
- VCCORLIB/Namespace not found::Platform::Value
dev_langs:
- C++
helpviewer_keywords:
- Platform::IBoxArray
ms.assetid: 6cd82c9e-4230-4147-9edb-7a652875dbf1
caps.latest.revision: 
author: ghogen
ms.author: ghogen
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: f52f8c95851ec80df41fe9f0838345cf46876227
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/14/2018
---
# <a name="platformiboxarray-interface"></a>Интерфейс Platform::IBoxArray
`IBoxArray` является оболочкой для массивов типов значений, передаваемых через двоичный интерфейс приложений (ABI) или хранящихся в коллекциях элементов `Platform::Object^` , таких как коллекции в элементах управления XAML.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
template <typename T>  
interface class IBoxArray  
```  
  
#### <a name="parameters"></a>Параметры  
 `T`  
 Тип упакованного значение в каждом элементе массива.  
  
### <a name="remarks"></a>Примечания  
 `IBoxArray` является C + +/ CX имя `Windows::Foundation::IReferenceArray`.  
  
### <a name="members"></a>Участники  
 Интерфейс `IBoxArray` наследует от интерфейса `IValueType` . Интерфейс`IBoxArray` также содержит следующие члены:  
  
|Метод|Описание:|  
|------------|-----------------|  
|[Значение](#value)|Возвращает распакованный массив, который ранее хранился в этом экземпляре `IBoxArray` .|  

## <a name="value"></a> Свойство IBoxArray::Value
Возвращает значение, которое было изначально сохранено в этом объекте.  
  
### <a name="syntax"></a>Синтаксис  
  
```cpp  
property T Value {T get();}  
```  
  
### <a name="parameters"></a>Параметры  
 `T`  
 Введите запакованное значение.  
  
### <a name="property-valuereturn-value"></a>Значение свойства, возвращаемое значение  
 Возвращает значение, которое было изначально сохранено в этом объекте.  
  
### <a name="remarks"></a>Примечания  
 Пример см. в разделе [упаковка-преобразование](../cppcx/boxing-c-cx.md).  
  
  
## <a name="see-also"></a>См. также  
 [Классы Array и WriteOnlyArray](../cppcx/array-and-writeonlyarray-c-cx.md)