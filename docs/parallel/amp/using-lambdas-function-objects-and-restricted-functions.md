---
title: Использование лямбда-выражений, объектов функций и ограниченных функций
ms.date: 11/04/2016
ms.assetid: 25346cc9-869d-4ada-aad3-e2228cad3d6c
ms.openlocfilehash: 819605eac6408751456479fbc3daa38aac1418ea
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50629402"
---
# <a name="using-lambdas-function-objects-and-restricted-functions"></a>Использование лямбда-выражений, объектов функций и ограниченных функций

Код C++ AMP, который вы хотите запустить на ускорителе заданное в качестве аргумента в вызове [parallel_for_each](reference/concurrency-namespace-functions-amp.md#parallel_for_each) метод. Можно предоставить лямбда-выражение или объект функции (функтор) в качестве этого аргумента. Кроме того лямбда-выражение выражение или объект функции могут вызывать функции с описателем ограничения C++ AMP. В этом разделе использует алгоритм сложения массивов для демонстрации лямбда-выражений, объектов функций и ограниченных функций. В следующем примере алгоритм без кода C++ AMP. Создаются два одномерных массива одинаковой длины. Соответствующие элементы целого типа добавляются и хранятся в третьем одномерным массивом. C++ AMP не используется.

```cpp
void CpuMethod() {

    int aCPP[] = {1, 2, 3, 4, 5};
    int bCPP[] = {6, 7, 8, 9, 10};
    int sumCPP[5];

    for (int idx = 0; idx <5; idx++)
    {
        sumCPP[idx] = aCPP[idx] + bCPP[idx];
    }

    for (int idx = 0; idx <5; idx++)
    {
        std::cout <<sumCPP[idx] <<"\n";
    }
}
```

## <a name="lambda-expression"></a>Лямбда-выражения

С помощью лямбда-выражение — это самый простой способ использования C++ AMP для переработки кода.

```cpp
void AddArraysWithLambda() {
    int aCPP[] = {1, 2, 3, 4, 5};
    int bCPP[] = {6, 7, 8, 9, 10};
    int sumCPP[5];

    array_view<const int, 1> a(5, aCPP);

    array_view<const int, 1> b(5, bCPP);

    array_view<int, 1> sum(5, sumCPP);

    sum.discard_data();

    parallel_for_each(
        sum.extent,
        [=](index<1> idx) restrict(amp)
        {
             sum[idx] = a[idx] + b[idx];
        });

    for (int i = 0; i <5; i++) {
        std::cout <<sum[i] <<"\n";
    }
}
```

Лямбда-выражение должно включать один параметр индексирования и должен включать `restrict(amp)`. В примере [array_view](../../parallel/amp/reference/array-view-class.md) `sum` объект имеет ранг 1. Таким образом, параметр в лямбда-выражении, [индекс](../../parallel/amp/reference/index-class.md) , имеющий ранг 1. Во время выполнения лямбда-выражение выполняется один раз для каждого элемента в [array_view](../../parallel/amp/reference/array-view-class.md) объекта. Дополнительные сведения см. в разделе [синтаксис лямбда-выражений](../../cpp/lambda-expression-syntax.md).

## <a name="function-object"></a>Объект Function

Можно вынести код ускорителя в объект функции.

```cpp
class AdditionFunctionObject
{
public:
    AdditionFunctionObject(const array_view<int, 1>& a,
    const array_view<int, 1>& b,
    const array_view<int, 1>& sum)
    : a(a), b(b), sum(sum)
    {
    }

    void operator()(index<1> idx) restrict(amp)
    {
        sum[idx] = a[idx] + b[idx];
    }

private:
    array_view<int, 1> a;
    array_view<int, 1> b;
    array_view<int, 1> sum;
};

void AddArraysWithFunctionObject() {
    int aCPP[] = {1, 2, 3, 4, 5};
    int bCPP[] = {6, 7, 8, 9, 10};
    int sumCPP[5];

    array_view<const int, 1> a(5, aCPP);

    array_view<const int, 1> b(5, bCPP);

    array_view<int, 1> sum(5, sumCPP);

    sum.discard_data();

    parallel_for_each(
        sum.extent,
        AdditionFunctionObject(a, b, sum));

    for (int i = 0; i <5; i++) {
        std::cout <<sum[i] <<"\n";
    }
}
```

Объект функции должен включать конструктор и перегрузку оператора вызова функции. Оператор вызова функции должен включать один параметр индексирования. Экземпляр объекта функции передается в качестве второго аргумента [parallel_for_each](reference/concurrency-namespace-functions-amp.md#parallel_for_each) метод. В этом примере три [array_view](../../parallel/amp/reference/array-view-class.md) объекты передаются в конструктор объекта функции. [Array_view](../../parallel/amp/reference/array-view-class.md) объект `sum` имеет ранг 1. Таким образом, параметр оператор вызова функции, [индекс](../../parallel/amp/reference/index-class.md) , имеющий ранг 1. Во время выполнения функция выполняется один раз для каждого элемента в [array_view](../../parallel/amp/reference/array-view-class.md) объекта. Дополнительные сведения см. в разделе [вызовов функций](../../cpp/function-call-cpp.md) и [объекты-функции в стандартной библиотеке C++](../../standard-library/function-objects-in-the-stl.md).

## <a name="c-amp-restricted-function"></a>C++ AMP-ограниченную функцию

Можно и дальше факторизовать код ускорителя, создавая ограниченную функцию и вызов его из лямбда-выражение или объект функции. В следующем примере кода показано, как вызывать ограниченную функцию из лямбда-выражения.

```cpp
void AddElementsWithRestrictedFunction(index<1> idx, array_view<int, 1> sum, array_view<int, 1> a, array_view<int, 1> b) restrict(amp)
{
    sum[idx] = a[idx] + b[idx];
}

void AddArraysWithFunction() {

    int aCPP[] = {1, 2, 3, 4, 5};
    int bCPP[] = {6, 7, 8, 9, 10};
    int sumCPP[5];

    array_view<int, 1> a(5, aCPP);

    array_view<int, 1> b(5, bCPP);

    array_view<int, 1> sum(5, sumCPP);

    sum.discard_data();

    parallel_for_each(
        sum.extent,
        [=](index<1> idx) restrict(amp)
        {
            AddElementsWithRestrictedFunction(idx, sum, a, b);
        });

    for (int i = 0; i <5; i++) {
        std::cout <<sum[i] <<"\n";
    }
}
```

Ограниченная функция должна включать `restrict(amp)` и ограничений, описанных в [ограничения (C++ AMP)](../../cpp/restrict-cpp-amp.md).

## <a name="see-also"></a>См. также

[C++ AMP (C++ Accelerated Massive Parallelism)](../../parallel/amp/cpp-amp-cpp-accelerated-massive-parallelism.md)<br/>
[Синтаксис лямбда-выражений](../../cpp/lambda-expression-syntax.md)<br/>
[Вызов функции](../../cpp/function-call-cpp.md)<br/>
[Объекты функции в стандартной библиотеке C++](../../standard-library/function-objects-in-the-stl.md)<br/>
[restrict (C++ AMP)](../../cpp/restrict-cpp-amp.md)