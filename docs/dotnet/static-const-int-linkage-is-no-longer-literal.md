---
title: Компоновка статической константы Int больше не является литералом | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- literal attribute [C++]
- constants, declaring
- integral constant expressions
ms.assetid: d2a5e3d2-ffb0-4b61-8114-bec5993a1195
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: cc3f72080c08807026c6458979ac0ba561e298df
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33165000"
---
# <a name="static-const-int-linkage-is-no-longer-literal"></a>Компоновка статической константы Int больше не является литералом
Объявление констант член класса отличается от управляемых расширений для C++ к Visual C++.  
  
 Несмотря на то что `static const` целочисленные члены по-прежнему поддерживаются, их атрибут компоновки изменился. Прежний атрибут компоновки теперь выражается элемента целочисленного литерала. Например рассмотрим следующий класс управляемых расширений:  
  
```  
public __gc class Constants {  
public:  
   static const int LOG_DEBUG = 4;  
};  
```  
  
 При этом создается следующие основные атрибуты CIL для поля (Обратите внимание, атрибут-литерал).  
  
```  
.field public static literal int32   
modopt([Microsoft.VisualC]Microsoft.VisualC.IsConstModifier) STANDARD_CLIENT_PRX = int32(0x00000004)  
```  
  
 При этом по-прежнему компилируется в новом синтаксисе:  
  
```  
public ref class Constants {  
public:  
   static const int LOG_DEBUG = 4;  
};  
```  
  
 оно больше не генерирует атрибут-литерал и поэтому не отображается как константа в среде CLR:  
  
```  
.field public static int32 modopt([Microsoft.VisualC]Microsoft.VisualC.IsConstModifier) STANDARD_CLIENT_PRX = int32(0x00000004)  
```  
  
 Чтобы получить такой же межъязыковой атрибут-литерал, необходимо изменить объявление новым поддерживаемым `literal` элемент данных, следующим образом:  
  
```  
public ref class Constants {  
public:  
   literal int LOG_DEBUG = 4;  
};  
```  
  
## <a name="see-also"></a>См. также  
 [Объявления членов в пределах класса или интерфейса (C + +/ CLI)](../dotnet/member-declarations-within-a-class-or-interface-cpp-cli.md)   
 [Литерал](../windows/literal-cpp-component-extensions.md)