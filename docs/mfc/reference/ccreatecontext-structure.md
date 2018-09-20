---
title: Структура CCreateContext | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CCreateContext
dev_langs:
- C++
helpviewer_keywords:
- CCreateContext structure [MFC]
ms.assetid: 337a0e44-d910-49a8-afc0-c7207666a9dc
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 320f84a8c423c16c4647108af0154fe7c07ce653
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46447301"
---
# <a name="ccreatecontext-structure"></a>Структура CCreateContext

Инфраструктура использует `CCreateContext` структуры при создании окна фрейма и представления, связанные с документом.

## <a name="syntax"></a>Синтаксис

```
struct CCreateContext
```

## <a name="remarks"></a>Примечания

`CCreateContext` представляет собой структуру и не имеет базового класса.

При создании окна, значения в этой структуре предоставляют сведения, используемые для соединения компонентов документа в представление данных. Необходимо использовать `CCreateContext` при переопределении части процесса создания.

Объект `CCreateContext` структура содержит указатели на документ, фрейм окна, представления и шаблон документа. Он также содержит указатель на `CRuntimeClass` , идентифицирующий тип представления для создания. Сведения о классе среды выполнения и указатель текущего документа используются для динамического создания нового представления. В следующей таблице приведен способ и время каждого `CCreateContext` член может использоваться:

|Член|Тип|Что такое для|
|------------|----------|--------------------|
|`m_pNewViewClass`|`CRuntimeClass*`|`CRuntimeClass` для создания нового представления.|
|`m_pCurrentDoc`|`CDocument*`|Существующий документ, связываемый с новым представлением.|
|`m_pNewDocTemplate`|`CDocTemplate*`|Шаблон документа, связанные с созданием нового окна фрейма MDI.|
|`m_pLastView`|`CView*`|Исходное представление, на котором моделируются дополнительные представления, как создавать представления окна разделителя или создание второе представление для документа.|
|`m_pCurrentFrame`|`CFrameWnd*`|Окна фрейма, на котором моделируются дополнительных фреймов, как и создания второго окна фрейма в документе.|

Когда шаблон документа создает документ и связанные с ней компоненты, он проверяет информацию, хранящуюся в `CCreateContext` структуры. Например представление не следует создавать для несуществующего документа.

> [!NOTE]
>  Все указатели в `CCreateContext` являются необязательными и могут быть `NULL` Если не задано или неизвестно.

`CCreateContext` используется функциями-членами, перечисленных в разделе «См. также.» Если вы планируете их переопределить, обратитесь к описания этих функций для получения конкретных сведений.

Ниже приведены несколько общих рекомендаций.

- При передаче в качестве аргумента для создания окна, как показано на `CWnd::Create`, `CFrameWnd::Create`, и `CFrameWnd::LoadFrame`, создать контекст определяет, что новые окна должны быть подключены к. Для большинства окон всю структуру является необязательным и `NULL` указатель может быть передан.

- Для функций-членов переопределяемый такие как `CFrameWnd::OnCreateClient`, `CCreateContext` аргумент является необязательным.

- Для функций-членов участвующих в режиме создания, необходимо указать достаточно информации для создания представления. Например для первого представления в окне разделителя, необходимо указать сведения о классе представление и текущего документа.

Как правило, при использовании значения по умолчанию framework, можно игнорировать `CCreateContext`. Если вы попытаетесь дополнительные изменения, исходный код библиотеки Microsoft Foundation Class или примеров программ, таких как приложения, поможет вам. Если вы забыли обязательного параметра, это утверждение framework сообщит, вы забыли.

Дополнительные сведения о `CCreateContext`, см. пример для MFC [VIEWEX](../../visual-cpp-samples.md).

## <a name="requirements"></a>Требования

**Заголовок:** afxext.h

## <a name="see-also"></a>См. также

[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[CFrameWnd::Create](../../mfc/reference/cframewnd-class.md#create)<br/>
[CFrameWnd::LoadFrame](../../mfc/reference/cframewnd-class.md#loadframe)<br/>
[CFrameWnd::OnCreateClient](../../mfc/reference/cframewnd-class.md#oncreateclient)<br/>
[CSplitterWnd::Create](../../mfc/reference/csplitterwnd-class.md#create)<br/>
[CSplitterWnd::CreateView](../../mfc/reference/csplitterwnd-class.md#createview)<br/>
[CWnd::Create](../../mfc/reference/cwnd-class.md#create)

