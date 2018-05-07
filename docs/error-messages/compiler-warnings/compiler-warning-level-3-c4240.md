---
title: Предупреждение (уровень 3) C4240 компилятора | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4240
dev_langs:
- C++
helpviewer_keywords:
- C4240
ms.assetid: a2657cdb-18e1-493f-882b-4e10c0bca71d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 4f0691230454ffd935d67c99f58b857cdc1ce0f0
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-warning-level-3-c4240"></a>Предупреждение компилятора (уровень 3) C4240
использовано нестандартное расширение: уровень доступа «имя_класса» теперь задан как «спецификатор доступа», ранее он был определен как «спецификатор доступа»  
  
 В режиме совместимости с ANSI ([/Za](../../build/reference/za-ze-disable-language-extensions.md)), невозможно изменить параметры доступа к вложенным классом. При использовании расширений Майкрософт по умолчанию (/Ze) можно с помощью этого предупреждения.  
  
## <a name="example"></a>Пример  
  
```  
// C4240.cpp  
// compile with: /W3  
class X  
{  
private:  
   class N;  
public:  
   class N  
   {   // C4240  
   };  
};  
  
int main()  
{  
}  
```