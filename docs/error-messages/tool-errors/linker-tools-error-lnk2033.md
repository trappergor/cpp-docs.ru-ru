---
title: "Ошибка средств компоновщика LNK2033 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: LNK2033
dev_langs: C++
helpviewer_keywords: LNK2033
ms.assetid: d61db467-9328-4788-bf54-e2a20537f13f
caps.latest.revision: "3"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: bac0d88d8e1ba06c358a6a1dd410b861dc582cdc
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="linker-tools-error-lnk2033"></a>Ошибка средств компоновщика LNK2033
неразрешенная лексема typeref (лексема) для «тип»  
  
 Тип не имеет определения в метаданных MSIL.  
  
 Ошибка LNK2033 может возникнуть при компиляции с параметром **/CLR: safe** и где имеется опережающим объявлением для типа в модуле MSIL, где находятся ссылки на тип в модуль MSIL.  
  
 Тип должен быть определен в разделе **/CLR: safe**.  
  
 Дополнительные сведения см. в разделе [/clr (компиляция CLR)](../../build/reference/clr-common-language-runtime-compilation.md).  
  
## <a name="example"></a>Пример  
 Следующий пример приводит к возникновению ошибки LNK2033.  
  
```  
// LNK2033.cpp  
// compile with: /clr:safe  
// LNK2033 expected  
ref class A;  
ref class B {};  
  
int main() {  
   A ^ aa = nullptr;  
   B ^ bb = nullptr;   // OK  
};  
```