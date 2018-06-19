---
title: Ошибка средств компоновщика LNK1237 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- LNK1237
dev_langs:
- C++
helpviewer_keywords:
- LNK1237
ms.assetid: 8722ffa8-096a-4bb0-85f9-f3aa0e10872a
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 1ffc337d6b1548db4717dc4b87ff8aa25ef92e93
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33298620"
---
# <a name="linker-tools-error-lnk1237"></a>Ошибка средств компоновщика LNK1237
При создании кода компилятор ввел ссылку на символ «символ», определенный в модуле «модуль», откомпилированном с параметром /GL  
  
 При создании кода компилятор не должен вводить символы, которые позднее разрешаются в скомпилированных определения **/GL**. `symbol` — это символ, введенный и позднее разрешенный для определения, скомпилированного с **/GL**.  
  
 Дополнительные сведения см. в разделе [/GL (оптимизация всей программы)](../../build/reference/gl-whole-program-optimization.md).  
  
 Чтобы устранить ошибку LNK1237, не компилируйте символ с **/GL** или использовать [/Include (Force Symbol References)](../../build/reference/include-force-symbol-references.md) для принудительного создания ссылки на символ.  
  
## <a name="example"></a>Пример  
 Следующий пример приводит к возникновению ошибки LNK1237. Чтобы устранить эту ошибку, не инициализируйте массив в файле LNK1237_a.cpp и добавьте **/ include: __chkstk** к команде link.  
  
```  
// LNK1237_a.cpp  
int main() {  
   char c[5000] = {0};  
}  
```  
  
```  
// LNK1237_b.cpp  
// compile with: /GS- /GL /c LNK1237_a.cpp  
// processor: x86  
// post-build command: (lib LNK1237_b.obj /LTCG & link LNK1237_a.obj LNK1237_b.lib /nodefaultlib /entry:main /LTCG)  
extern "C" void _chkstk(size_t s) {}  
```