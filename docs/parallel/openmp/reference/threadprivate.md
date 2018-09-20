---
title: threadprivate | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: reference
f1_keywords:
- threadprivate
dev_langs:
- C++
helpviewer_keywords:
- threadprivate OpenMP directive
ms.assetid: 3515aaed-6f9d-4d59-85eb-342378bea2d3
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: a9313934744f6eae66736f25b0d0b8592743cf12
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46376984"
---
# <a name="threadprivate"></a>threadprivate

Указывает, что переменная является частной для потока.

## <a name="syntax"></a>Синтаксис

```
#pragma omp threadprivate(var)
```

### <a name="parameters"></a>Параметры

*var*<br/>
Разделенный запятыми список переменных, которые вы хотите сделать частными потоку. `var` должен быть переменной глобального - или действующую в пространстве имен или статической локальной переменной.

## <a name="remarks"></a>Примечания

`threadprivate` Директива поддерживает без предложения OpenMP.

Дополнительные сведения см. в разделе [2.7.1 директива threadprivate](../../../parallel/openmp/2-7-1-threadprivate-directive.md).

`threadprivate` Директива основан на [поток](../../../cpp/thread.md) `__declspec` атрибут; ограничения на **__declspec(thread)** применяются к `threadprivate`.

Нельзя использовать `threadprivate` в любой библиотеки DLL, которые будут загружены через [LoadLibrary](https://msdn.microsoft.com/library/windows/desktop/ms684175).  Сюда входят библиотек DLL, загружаемых с [/DELAYLOAD (Импорт отложенной загрузки)](../../../build/reference/delayload-delay-load-import.md), который также используется **LoadLibrary**.

Можно использовать `threadprivate` в библиотеку DLL, которая загружается статически при запуске процесса.

Так как `threadprivate` основан на **__declspec(thread)**, `threadprivate` переменной будет существовать в любом потоке, в процессе работы не только эти потоки, которые являются частью группы потоков, сформированными параллельной области.  Это деталь реализации, может потребоваться следует учитывать, так как вы могли заметить, например, конструкторы для `threadprivate` определяемого пользователем типа вызывается дополнительные чаще, чем ожидалось.

Объект `threadprivate` переменной destructable типа не обязательно иметь его деструктор вызывается.  Пример:

```
struct MyType
{
    ~MyType();
};

MyType threaded_var;
#pragma omp threadprivate(threaded_var)
int main()
{
    #pragma omp parallel
    {}
}
```

Пользователи не имеют контроля о том, когда прекращается при обнаружении потоков, образующей область параллельной обработки.  Если при завершении процесса, потоки не будут отображаться уведомления о выходе процесса и деструктор не будет вызываться для существует этих потоков `threaded_var` в любом потоке, за исключением того, который завершает работу (в данном случае — основной поток).  Чтобы код не следует полагаться на правильное уничтожение `threadprivate` переменные.

## <a name="example"></a>Пример

Пример использования `threadprivate`, см. в разделе [частного](../../../parallel/openmp/reference/private-openmp.md).

## <a name="see-also"></a>См. также

[Директивы](../../../parallel/openmp/reference/openmp-directives.md)