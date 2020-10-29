---
title: Использование наборов правил для задания выполняемых правил C++
ms.date: 07/27/2020
ms.topic: conceptual
f1_keywords:
- vs.codeanalysis.rulesets.native
ms.openlocfilehash: 53e1122cd1aac74401ca956ee24ebcdf79883228
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/29/2020
ms.locfileid: "92921910"
---
# <a name="use-rule-sets-to-specify-the-c-rules-to-run"></a>Использование наборов правил для задания выполняемых правил C++

В Visual Studio можно создать и изменить набор настраиваемых *правил* для удовлетворения конкретных потребностей проекта, связанных с анализом кода. Наборы правил по умолчанию хранятся в *`%VSINSTALLDIR%\Team Tools\Static Analysis Tools\Rule Sets`* .

**Visual Studio 2017 версии 15,7 и более поздних версий:** Пользовательские наборы правил можно создавать с помощью любого текстового редактора и применять их в сборках из командной строки независимо от используемой системы сборки. Дополнительные сведения см. в статье [`/analyze:ruleset`](../build/reference/analyze-code-analysis.md).

Чтобы создать настраиваемый набор правил C++ в Visual Studio, в интегрированной среде разработки Visual Studio должен быть открыт проект C/C++. Затем вы открываете стандартный набор правил в редакторе набора правил, а затем добавляете или удаляете определенные правила и при необходимости изменяете действие, которое происходит, когда анализ кода определяет нарушение правила.

Чтобы создать новый настраиваемый набор правил, сохраните его с новым именем файла. Настраиваемый набор правил автоматически назначается проекту.

## <a name="to-create-a-custom-rule-from-a-single-existing-rule-set"></a>Создание настраиваемого правила на основе одного существующего набора правил

::: moniker range="<=msvc-150"

1. В обозреватель решений откройте контекстное меню проекта и выберите пункт **Свойства** .

1. В диалоговом окне **страницы свойств** перейдите на страницу свойств **Свойства конфигурации** > **Code Analysis** > **Общие** свойства анализ кода.

1. В раскрывающемся списке **набор правил** выполните одно из следующих действий.

   - Выберите набор правил, который требуется настроить.

     \- или -

   - Выберите **\<Browse...>** , чтобы указать существующий набор правил, которого нет в списке.

1. Нажмите кнопку **Открыть** , чтобы отобразить правила в редакторе набора правил.

::: moniker-end
::: moniker range=">=msvc-160"

1. В обозреватель решений откройте контекстное меню проекта и выберите пункт **Свойства** .

1. В диалоговом окне **страницы свойств** откройте страницу свойств **Конфигурация** > **анализ кода** свойства > **Майкрософт** .

1. В раскрывающемся списке **активные правила** выполните одно из следующих действий.

   - Выберите набор правил, который требуется настроить.

     \- или -

   - Выберите **\<Browse...>** , чтобы указать существующий набор правил, которого нет в списке.

1. Нажмите кнопку **Открыть** , чтобы отобразить правила в редакторе набора правил.

::: moniker-end

## <a name="to-modify-a-rule-set-in-the-rule-set-editor"></a>Изменение набора правил в редакторе набора правил

- Чтобы изменить отображаемое имя набора правил, в меню **вид** выберите пункт **окно свойств** . Введите отображаемое имя в поле **имя** . Обратите внимание, что отображаемое имя может отличаться от имени файла.

- Чтобы добавить все правила группы в настраиваемый набор правил, установите флажок для группы. Чтобы удалить все правила группы, снимите флажок.

- Чтобы добавить определенное правило в набор настраиваемых правил, установите флажок для этого правила. Чтобы удалить правило из набора правил, снимите флажок.

- Чтобы изменить действие, выполняемое при нарушении правила анализа кода, выберите поле **действия** для правила и выберите одно из следующих значений:

     **Предупреждение** — выдает предупреждение.

     **Ошибка** -выдает ошибку.

     **Info** — создает сообщение.

     **Нет** — отключает правило. Это действие аналогично удалению правила из набора правил.

## <a name="to-group-filter-or-change-the-fields-in-the-rule-set-editor-by-using-the-rule-set-editor-toolbar"></a>Группирование, фильтрация или изменение полей в редакторе набора правил с помощью панели инструментов редактора набора правил

- Чтобы развернуть правила во всех группах, выберите **Развернуть все** .

- Чтобы свернуть правила во всех группах, выберите **Свернуть все** .

- Чтобы изменить поле, по которому группируются правила, выберите поле в списке **Группировать по** . Чтобы отобразить правила, разгруппированные, выберите **\<None>** .

- Чтобы добавить или удалить поля в столбцах правил, выберите **Параметры столбцов** .

- Чтобы скрыть правила, которые не применяются к текущему решению, выберите **Скрыть правила, которые не применяются к текущему решению** .

- Чтобы переключиться между отображением и скрытием правил, которым назначено действие ошибка, выберите **Показать правила, которые могут формировать ошибки анализа кода** .

- Чтобы переключиться между отображением и скрытием правил, которым назначено действие предупреждение, выберите **Показать правила, которые могут формировать предупреждения анализа кода** .

- Чтобы переключиться между отображением и скрытием правил, которым назначено действие **нет** , выберите **Показать правила, которые не включены** .

- Чтобы добавить или удалить наборы правил Майкрософт по умолчанию для текущего набора правил, выберите **Добавить или удалить дочерние наборы правил** .

## <a name="to-create-a-rule-set-in-a-text-editor"></a>Создание набора правил в текстовом редакторе

Вы можете создать настраиваемый набор правил в текстовом редакторе, сохранить его в любом расположении с *`.ruleset`* расширением и применить в с [`/analyze:ruleset`](../build/reference/analyze-code-analysis.md) параметром компилятора.

В следующем примере показан базовый файл набора правил, который можно использовать в качестве отправной точки:

```xml
<?xml version="1.0" encoding="utf-8"?>
<RuleSet Name="New Rule Set" Description="New rules to apply." ToolsVersion="10.0">
  <Rules AnalyzerId="Microsoft.Analyzers.NativeCodeAnalysis" RuleNamespace="Microsoft.Rules.Native">
    <Rule Id="C6001" Action="Warning" />
    <Rule Id="C26494" Action="Warning" />
  </Rules>
</RuleSet>
```

## <a name="ruleset-schema"></a>Схема набора правил

Следующая схема набора правил описывает схему XML-файла набора правил. Схема набора правил хранится в *`%VSINSTALLDIR%\Team Tools\Static Analysis Tools\Schemas\RuleSet.xsd`* . Его можно использовать для создания собственных наборов правил программным способом или для проверки соответствия пользовательских наборов правил правильному формату. Дополнительные сведения см. [в разделе инструкции. Создание XML-документа на основе схемы XSD](/visualstudio/xml-tools/how-to-create-an-xml-document-based-on-an-xsd-schema).

```xml
<?xml version="1.0" encoding="utf-8"?>
<xs:schema xmlns:xs="http://www.w3.org/2001/XMLSchema">

  <xs:annotation>
    <xs:documentation xml:lang="en">
            Visual Studio Code Analysis Rule Set Schema Definition Language.
            Copyright (c) Microsoft Corporation. All rights reserved.
        </xs:documentation>
  </xs:annotation>

  <!-- Every time this file changes, be sure to change the Validate method for the corresponding object in the code -->

  <xs:element name="RuleSet" type="TRuleSet">
  </xs:element>

  <xs:complexType name="TLocalization">
    <xs:all>
      <xs:element name="Name" type="TName" minOccurs="0" maxOccurs="1" />
      <xs:element name="Description" type="TDescription" minOccurs="0" maxOccurs="1" />
    </xs:all>
    <xs:attribute name="ResourceAssembly" type="TNonEmptyString" use="required" />
    <xs:attribute name="ResourceBaseName" type="TNonEmptyString" use="required" />
  </xs:complexType>

  <xs:complexType name="TRuleHintPaths">
    <xs:sequence>
      <xs:element name="Path" type="TNonEmptyString" minOccurs="0" maxOccurs="unbounded" />
    </xs:sequence>
  </xs:complexType>
  
  <xs:complexType name="TName">
    <xs:attribute name="Resource" type="TNonEmptyString" use="required" />
  </xs:complexType>

  <xs:complexType name="TDescription">
    <xs:attribute name="Resource" type="TNonEmptyString" use="required" />
  </xs:complexType>

  <xs:complexType name="TInclude">
    <xs:attribute name="Path" type="TNonEmptyString" use="required" />
    <xs:attribute name="Action" type="TIncludeAction" use="required" />
  </xs:complexType>

  <xs:complexType name="TIncludeAll">
    <xs:attribute name="Action" type="TIncludeAllAction" use="required" />
  </xs:complexType>

  <xs:complexType name="TRule">
    <xs:attribute name="Id" type="TNonEmptyString" use="required" />
    <xs:attribute name="Action" type="TRuleAction" use="required" />
  </xs:complexType>

  <xs:complexType name="TRules">
    <xs:sequence>
      <xs:element name="Rule" type="TRule" minOccurs="0" maxOccurs="unbounded" />
    </xs:sequence>
    <xs:attribute name="AnalyzerId" type="TNonEmptyString" use="required" />
    <xs:attribute name="RuleNamespace" type="TNonEmptyString" use="required" />
  </xs:complexType>

  <xs:complexType name="TRuleSet">
    <xs:sequence minOccurs="0" maxOccurs="1">
      <xs:element name="Localization" type="TLocalization" minOccurs="0" maxOccurs="1" />
      <xs:element name="RuleHintPaths" type="TRuleHintPaths" minOccurs="0" maxOccurs="1" />
      <xs:element name="IncludeAll" type="TIncludeAll" minOccurs="0" maxOccurs="1" />
      <xs:choice minOccurs="0" maxOccurs="unbounded">
        <xs:element name="Include" type="TInclude" minOccurs="0" maxOccurs="unbounded" />
        <xs:element name="Rules" type="TRules" minOccurs="0" maxOccurs="unbounded">
          <xs:unique name="UniqueRuleName">
            <xs:selector xpath="Rule" />
            <xs:field xpath="@Id" />
          </xs:unique>
        </xs:element>
      </xs:choice>
    </xs:sequence>
    <xs:attribute name="Name" type="TNonEmptyString" use="required" />
    <xs:attribute name="Description" type="xs:string" use="optional" />
    <xs:attribute name="ToolsVersion" type="TNonEmptyString" use="required" />
  </xs:complexType>

  <xs:simpleType name="TRuleAction">
    <xs:restriction base="xs:string">
      <xs:enumeration value="Error"/>
      <xs:enumeration value="Warning"/>
      <xs:enumeration value="Info"/>
      <xs:enumeration value="Hidden"/>
      <xs:enumeration value="None"/>
    </xs:restriction>
  </xs:simpleType>

  <xs:simpleType name="TIncludeAction">
    <xs:restriction base="xs:string">
      <xs:enumeration value="Error"/>
      <xs:enumeration value="Warning"/>
      <xs:enumeration value="Info"/>
      <xs:enumeration value="Hidden"/>
      <xs:enumeration value="None"/>
      <xs:enumeration value="Default"/>
    </xs:restriction>
  </xs:simpleType>

  <xs:simpleType name="TIncludeAllAction">
    <xs:restriction base="xs:string">
      <xs:enumeration value="Error"/>
      <xs:enumeration value="Warning"/>
      <xs:enumeration value="Info"/>
      <xs:enumeration value="Hidden"/>
    </xs:restriction>
  </xs:simpleType>

  <xs:simpleType name="TNonEmptyString">
    <xs:restriction base="xs:string">
      <xs:minLength value="1" />
    </xs:restriction>
  </xs:simpleType>
  
</xs:schema>

```

Сведения об элементе схемы:

| Schema, элемент | Описание |
|--------------------|--------------|
| `TLocalization` | Сведения о локализации, включая имя файла набора правил, описание файла набора правил, имя сборки ресурса, содержащей локализованный ресурс, и базовое имя локализованного ресурса. |
| `TRuleHintPaths` | Пути к файлам, используемые в качестве подсказок для поиска файлов набора правил |
| `TName` | Имя текущего файла RuleSet |
| `TDescription` | Описание текущего файла RuleSet |
| `TInclude` | Путь к включаемому набору правил с действием правила |
| `TIncludeAll` | Действие правила для всех правил |
| `TRule` | Идентификатор правила с действием правила |
| `TRules` | Коллекция из одного или нескольких правил |
| `TRuleSet` | Формат RuleSet File, состоящий из сведений о локализации, путей указания правил, включения всей информации, включения сведений, сведений о правилах, имени, описания и сведений о версии инструментов |
| `TRuleAction` | Перечисление, описывающее действие правила, такое как ошибка, предупреждение, информация, скрыто или нет |
| `TIncludeAction` | Перечисление, описывающее действие правила, такое как ошибка, предупреждение, сведения, скрытые, нет или по умолчанию |
| `TIncludeAllAction` | Перечисление, описывающее действие правила, например ошибки, предупреждения, сведения или скрытые |

Пример набора правил см. в разделе [Создание набора правил в текстовом редакторе](#to-create-a-rule-set-in-a-text-editor)или любого набора правил по умолчанию, хранящегося в `%VSINSTALLDIR%\Team Tools\Static Analysis Tools\Rule Sets` .
