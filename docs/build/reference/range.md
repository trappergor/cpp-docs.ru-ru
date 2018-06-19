---
title: — ДИАПАЗОН | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /RANGE
dev_langs:
- C++
helpviewer_keywords:
- /RANGE dumpbin option
- -RANGE dumpbin option
ms.assetid: 7eeba266-32be-49cc-a350-96bdf541f98a
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d06d699500ba3ea441af61a2e2a5a0da3f96903a
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
ms.locfileid: "32374428"
---
# <a name="range"></a>Параметр /RANGE
Изменяет вывод свойства dumpbin при совместном использовании с другими параметрами dumpbin, например/RAWDATA или/DISASM.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
/RANGE:vaMin[,vaMax]  
```  
  
## <a name="flags"></a>Флаги  
 **vaMin**  
 Виртуальный адрес, с которого начинается операция dumpbin.  
  
 **vaMax** (необязательно)  
 Виртуальный адрес, по которому операция dumpbin для завершения. Если не указан, программа dumpbin переместится в конец файла.  
  
## <a name="remarks"></a>Примечания  
 Чтобы просмотреть виртуальные адреса образа, используйте файл отображения образа (RVA + базовый адрес), **/DISASM** или **/Headers** параметр программы dumpbin, или Дизассемблированный код в отладчике Visual Studio.  
  
## <a name="example"></a>Пример  
 В этом примере **/диапазон** используется для изменения способа отображения **/DISASM** параметр. В этом примере начальное значение выражается как десятичное число, и конечное значение указывается в виде шестнадцатеричного числа.  
  
```  
dumpbin /disasm /range:4219334,0x004061CD t.exe  
```  
  
## <a name="see-also"></a>См. также  
 [Параметры DUMPBIN](../../build/reference/dumpbin-options.md)