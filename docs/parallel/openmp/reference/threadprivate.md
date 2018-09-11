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
ms.openlocfilehash: 0502528a2db47b8db41437fd7017aece1dc67cde
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/29/2018
ms.locfileid: "43217749"
---
# <a name="threadprivate"></a>threadprivate
Указывает, что переменная является частной для потока.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
#pragma omp threadprivate(var)  
```  
  
## <a name="remarks"></a>Примечания  
 где  
  
 `var`  
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