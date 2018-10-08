---
title: Что делает объект ATL Noncreatable | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- vc.appwiz.ATL.objects
dev_langs:
- C++
helpviewer_keywords:
- noncreatable ATL objects
- ATL projects, noncreatable objects
ms.assetid: 80d0bca2-dea0-4801-9a85-6243124437f6
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: f0b20cbae3036ffecfa63f2e3ee6be8e2153fc8f
ms.sourcegitcommit: 997e6b7d336cddb388bb6e9e56527725fcaa0624
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/08/2018
ms.locfileid: "48860918"
---
# <a name="making-an-atl-object-noncreatable"></a>Что делает Noncreatable объекта ATL

Атрибуты на основе ATL COM-объекта можно изменить таким образом, чтобы клиент не может напрямую создать объект. В этом случае объект будет возвращенные с помощью вызова метода на другом объекте, а не создается непосредственно.

## <a name="to-make-an-object-noncreatable"></a>Чтобы сделать объект noncreatable

1. Удалить [OBJECT_ENTRY_AUTO](object-map-macros.md#object_entry_auto) для объекта. Если объект noncreatable, но Регистрируемый элемент управления, замените OBJECT_ENTRY_AUTO с [OBJECT_ENTRY_NON_CREATEABLE_EX_AUTO](object-map-macros.md#object_entry_non_createable_ex_auto).

1. Добавить [noncreatable](../../windows/noncreatable.md) атрибут coclass в IDL-файл. Пример:

    ```  
    [uuid(A1992E3D-3CF0-11D0-826F-00A0C90F2851), 
    helpstring("MyObject"), 
    noncreatable]  
    coclass MyObject  
    {  
        [default] interface IMyInterface;  
    }  
    ```

## <a name="see-also"></a>См. также

[Мастер проектов ATL](../../atl/reference/atl-project-wizard.md)<br/>
[Типы проектов Visual C++](../../ide/visual-cpp-project-types.md)<br/>
[Создание проектов для рабочего стола с помощью мастеров приложений](../../ide/creating-desktop-projects-by-using-application-wizards.md)<br/>
[Программирование с использованием ATL и кода среды выполнения C](../../atl/programming-with-atl-and-c-run-time-code.md)<br/>
[Основы COM-объектов ATL](../../atl/fundamentals-of-atl-com-objects.md)<br/>
[Конфигурации проектов ATL по умолчанию](../../atl/reference/default-atl-project-configurations.md)
