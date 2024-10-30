### Stats
- Time for start up: 4.86s
- Rerun test: 800ms

### Mocking Objects
vi.mock run the mock before any other code
```ts
vi.mock('../hooks/language-select', () => ({
  useLanguageSelectHook: () => {
    const [currentLanguage, setCurrentLanguage] = useState<string>('en');

    return {
      supportedLanguages: ['en', 'es'],
      setSelectedLanguage: (lng: string) => setCurrentLanguage(lng),
      getSelectedLanguage: (): string | undefined => currentLanguage,
    }
  },
}));
```
### Setting up test
Description: Test are set up similar to jest. You'll use describes to setup a block of test, it to define the individual test case, and expect to perform any required assertions.

```ts
describe('Display component', () => {
  afterEach(() => { vi.clearAllMocks(); });

  it('Changes language successfully', () => {
    // Arrange
    render(<LanguageSelect />);
  
    // Act
    act(() => { 
      fireEvent.change(screen.getByRole('combobox'), { target: { value: 'es'} });
    });
  
    // Assert
    const selectElement = screen.getByRole('combobox') as HTMLSelectElement;
    expect(selectElement.value).toBe('es');
  });
});
```
