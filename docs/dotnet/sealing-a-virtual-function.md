---
title: Запечатывание виртуальной функции | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- sealed keyword [C++]
- derived classes, virtual functions
- virtual functions, sealing
- __sealed keyword
ms.assetid: 0e9fae03-6425-4512-9a24-8ccb6dc8a0d4
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 69ac614d55ade10b94621da2a3eb1c43d25ebaf5
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46385187"
---
# <a name="sealing-a-virtual-function"></a>Запечатывание виртуальной функции

Синтаксис Запечатывание виртуальной функции отличается от управляемых расширений для C++ в Visual C++.

`__sealed` Ключевое слово используется в управляемых расширений для изменения ссылочного типа, запрещая последующее наследование от него (см. в разделе [объявление типа управляемого класса](../dotnet/declaration-of-a-managed-class-type.md)), или изменить виртуальную функцию, отключение последующие переопределение метода в производном классе. Пример:

```
__gc class base { public: virtual void f(); };
__gc class derived : public base {
public:
   __sealed void f();
};
```

В этом примере `derived::f()` переопределяет `base::f()` экземпляра на основании точного соответствия прототипа функции. `__sealed` Слово указывает, что последующие класс, наследуемый от производного класса не допускается переопределение `derived::f()`.

В новом синтаксисе `sealed` размещается после подписи, а не появлялись в любом месте до фактического прототипа функции, ранее была разрешена. Кроме того, использование `sealed` требует явно использовать `virtual` также ключевое слово. То есть правильное преобразование `derived`выше, выглядит следующим образом:

```
ref class derived: public base {
public:
   virtual void f() override sealed;
};
```

Отсутствие `virtual` ключевое слово в данном экземпляре приводит к ошибке. В новом синтаксисе контекстное ключевое слово `abstract` может использоваться вместо `=0` для указания чистой виртуальной функции. Это не поддерживается в управляемых расширений. Пример:

```
__gc class base { public: virtual void f()=0; };
```

можно переписать следующим образом

```
ref class base { public: virtual void f() abstract; };
```

## <a name="see-also"></a>См. также

[Объявления членов в пределах класса или интерфейса (C++/CLI)](../dotnet/member-declarations-within-a-class-or-interface-cpp-cli.md)<br/>
[sealed](../windows/sealed-cpp-component-extensions.md)