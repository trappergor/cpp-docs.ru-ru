---
title: Спецификатор override
ms.date: 11/04/2016
helpviewer_keywords:
- override Identifier
ms.assetid: b286fb46-9374-4ad8-b2e7-4607119b6133
ms.openlocfilehash: 71505f8b9b4dc2800e80a78a64f0ca6984af1349
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50430034"
---
# <a name="override-specifier"></a>Спецификатор override

Можно использовать **переопределить** ключевое слово для назначения члена функции, которые переопределить виртуальную функцию в базовом классе.

## <a name="syntax"></a>Синтаксис

```
function-declaration override;
```

## <a name="remarks"></a>Примечания

**переопределить** является контекстным и имеет специальное значение, только если используется после объявления функции-члена; в противном случае он не является зарезервированным ключевым словом.

## <a name="example"></a>Пример

Используйте **переопределить** для предотвращения случайного поведения наследования в коде. В следующем примере показано where, не прибегая к **переопределить**, поведение функции-члена производного класса не может быть случайным. Компилятор не выдает ошибки при использовании этого кода.

```cpp
class BaseClass
{
    virtual void funcA();
    virtual void funcB() const;
    virtual void funcC(int = 0);
    void funcD();
};

class DerivedClass: public BaseClass
{
    virtual void funcA(); // ok, works as intended

    virtual void funcB(); // DerivedClass::funcB() is non-const, so it does not
                          // override BaseClass::funcB() const and it is a new member function

    virtual void funcC(double = 0.0); // DerivedClass::funcC(double) has a different
                                      // parameter type than BaseClass::funcC(int), so
                                      // DerivedClass::funcC(double) is a new member function
};
```

При использовании **переопределить**, компилятор создает ошибки, а не создает нового члена функции.

```cpp
class BaseClass
{
    virtual void funcA();
    virtual void funcB() const;
    virtual void funcC(int = 0);
    void funcD();
};

class DerivedClass: public BaseClass
{
    virtual void funcA() override; // ok

    virtual void funcB() override; // compiler error: DerivedClass::funcB() does not
                                   // override BaseClass::funcB() const

    virtual void funcC( double = 0.0 ) override; // compiler error:
                                                 // DerivedClass::funcC(double) does not
                                                 // override BaseClass::funcC(int)

    void funcD() override; // compiler error: DerivedClass::funcD() does not
                           // override the non-virtual BaseClass::funcD()
};
```

Чтобы указать, что функции не может быть переопределен и не может быть унаследован классами, используйте [окончательный](../cpp/final-specifier.md) ключевое слово.

## <a name="see-also"></a>См. также

[Описатель final](../cpp/final-specifier.md)<br/>
[Ключевые слова](../cpp/keywords-cpp.md)