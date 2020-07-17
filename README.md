### Установка
> Установить https://brew.sh/index_ru

> Установить Ruby 2.2 или выше https://gorails.com/setup/osx/10.14-mojave

> Выполнить `gem install generamba`

### Интеграция в проект

> Изменить project format на "Xcode 8.0-compatible"

> В файле "project.pbxproj" удалить строки `inputFileListPaths = ();` `outputFileListPaths = ();`

> Выполнить `generamba setup`

> Открыть 'Rambafile' добавить строки

```
### Templates
catalogs:
- 'git@gitlab.sequenia.com:templates/TemplatesIOS.git'`
```
> Проверить пути

```
# The file path for new modules
project_file_path: PROJECT_NAME/Modules

# The Xcode group path to new modules
project_group_path: PROJECT_NAME/Modules
```

> Выполнить `generamba template install`

### Установка шаблона
> Выполнить `generamba gen MODULE_NAME TEMPLATE_NAME`

# Snippets

### Use case

```
// MARK: - <# code #>
protocol <# code #>: class {
    func execute(completion: @escaping (_ success: Bool, <# code #>, _ error: String?) -> ())
}

// MARK: - <# code #>
class <# code #>: <# code #> {
    
// MARK: - <# code #>
    func execute(completion: @escaping (_ success: Bool, _ <# code #>, _ error: String?) -> ()) {
    }
}

```

### Table cell 

```
// MARK: - <# code #>

class <# code #>: UITableViewCell {

// MARK: - Outlets

// MARK: - Properties
    private var model: <# code #>!

// MARK: - Life Cycle
    override func awakeFromNib() {
        super.awakeFromNib()
    }
// MARK: - Bind
    func bind(model: <# code #>) {
        self.model = model
    }
}
```

### Model row table cell

```
import SQDifferenceKit

// MARK: - <# code #>
class <# code #>: ModelRow {

// MARK: - Properties

// MARK: - Inits
    convenience init(id: String) {
        self.init(id: id)
    }

// MARK: - SQDifferenceKit methods helpers
    override func isContentEqual(to source: ModelRow) -> Bool {
        guard let source = source as? <# code #> else { return false }
        return self.differenceIdentifier == source.differenceIdentifier
    }

    override func copy() -> ModelRow {
        return <# code #>(id: self.differenceIdentifier)
    }
}
```

### Table header

```
import SQDifferenceKit

// MARK: - <#code#>
protocol <#code#>: BaseTableHeaderProtocol {
}

// MARK: - <#code#>
class <#code#>: BaseHeader {

// MARK: - Outlets

// MARK: - Properties
    private var model: <#code#>!
    private weak var delegate: <#code#>?

// MARK: - Methods
    override func construct<T>(data: T, delegate: BaseTableHeaderProtocol? = nil) -> Self where T: ModelHeader {
        guard let model = data as? <#code#> else { return self }
        self.delegate = delegate as? <#code#>
        self.model = model
        self.configure()
        return self
    }
    
    func configure() {
    }
}
```
