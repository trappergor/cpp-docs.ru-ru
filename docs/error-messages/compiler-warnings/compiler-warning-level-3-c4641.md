---
title: Предупреждение компилятора (уровень 3) C4641 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4641
dev_langs:
- C++
helpviewer_keywords:
- C4641
ms.assetid: 28fe5c3e-6039-42da-9100-1312b5b15aea
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: f44e94868f6a7b379fb1a2f75bbd28ce011b54c9
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46112113"
---
# <a name="compiler-warning-level-3-c4641"></a>Предупреждение компилятора (уровень 3) C4641

в документирующем комментарии XML присутствует неоднозначная перекрестная ссылка

Компилятору не удалось однозначно разрешить ссылку. Чтобы устранить это предупреждение, укажите сведения о параметрах, необходимо сделать ссылку однозначной.

Дополнительные сведения см. в разделе [XML Documentation](../../ide/xml-documentation-visual-cpp.md).

## <a name="example"></a>Пример

Следующий пример приводит к возникновению ошибки C4641.

```
// C4641.cpp
// compile with: /W3 /doc /clr /c

/// <see cref="f" />   // C4641
// try the following line instead
// /// <see cref="f(int)" />
public ref class GR {
public:
   void f( int ) {}
   void f( char ) {}
};
```