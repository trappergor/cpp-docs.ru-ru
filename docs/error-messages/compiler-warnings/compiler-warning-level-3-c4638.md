---
title: Предупреждение компилятора (уровень 3) C4638 | Документация Майкрософт
ms.custom: ''
ms.date: 08/27/2018
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4638
dev_langs:
- C++
helpviewer_keywords:
- C4638
ms.assetid: 2c07923a-e103-4e40-bd11-fdfed428a5ec
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 29febc17f041fee27064fc085896c892eecd5c56
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/29/2018
ms.locfileid: "43198236"
---
# <a name="compiler-warning-level-3-c4638"></a>Предупреждение компилятора (уровень 3) C4638

> Цель комментария XML-документа: ссылка на неизвестный символ "*символ*"

## <a name="remarks"></a>Примечания

Компилятору не удалось разрешить символ (*символ*). Символ должен быть допустимым при компиляции.

## <a name="example"></a>Пример

В следующем примере возникает ошибка C4638.

```cpp
// C4638.cpp
// compile with: /clr /doc /LD /W3
using namespace System;

/// Text for class MyClass.
public ref class MyClass {
public:
   /// <summary> Text </summary>
   /// <see cref="aSymbolThatAppearsNowhereInMyProject"/>
   // Try the following line instead:
   // /// <see cref="System::Console::WriteLine"/>
   void MyMethod() {}
};   // C4638
```