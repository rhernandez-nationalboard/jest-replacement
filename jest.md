### Stats
- Suite Runtime: 4.2s

### Setting up test
Description: 'describe' setups a test suite, 'it' defines an individual test, and 'expect' is used to perform any required assertions

```ts
describe('Language Select Tests', () => {
  it('Changes language successfully', async () => {
    // Arrange
    render(<LanguageSelect />);
    const selectElement = screen.getByRole('combobox');

    // Act
    await userEvent.selectOptions(selectElement, 'es');

    // Assert
    expect(selectElement).toHaveValue('es'); 
  });
});
```

### Mocking Objects

```ts
jest.mock('../hooks/language-select', () => ({
  useLanguageSelectHook: (): LanguageSelectHookResponse => {
    const [currentLanguage, setCurrentLanguage] = useState<string | undefined>('en');

    return {
      supportedLanguages: ['en', 'es'],
      setSelectedLanguage: (lng: string | undefined) => setCurrentLanguage(lng),
      getSelectedLanguage: (): string | undefined => currentLanguage,
    }
  }
}));
```