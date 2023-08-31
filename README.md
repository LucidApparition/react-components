# React Component Library with Storybook
### This repo is a sandbox library for creating React components with the Storybook framework.
---
```css
.storybook-button--primary {
  color: white;
  background-color: #1ea7fd;
}
```

```typescript
export const Primary: Story = {
  args: {
    primary: true,
    label: 'Button',
  },
};
```

```tsx
/**
 * Primary UI component for user interaction
 */
export const Button = ({
  primary = false,
  size = 'medium',
  backgroundColor,
  label,
  ...props
}: ButtonProps) => {
  const mode = primary ? 'storybook-button--primary' : 'storybook-button--secondary';
  return (
    <button
      type="button"
      className={['storybook-button', `storybook-button--${size}`, mode].join(' ')}
      style={{ backgroundColor }}
      {...props}
    >
      {label}
    </button>
  );
};
```
---
![buttonDemo](https://github.com/LucidApparition/react-typescript/assets/104107496/be35c574-ad04-4141-b9d9-17eb9fa9bc2d)

---

## Setup

1. Clone the Repository:

   - Open your terminal.
   - Navigate to the directory where you want to clone the repository using the cd command.
   - Use the following command to clone your repository:
     
```bash 
git clone https://github.com/LucidApparition/react-typescript.git
```
   *If it doesn't work, try SSH or GitHubCLI. You can find this URL on the GitHub repository page, under the "Code" button.*

2. Navigate to the Repository

   - Change your terminal's current directory to the newly cloned repository:
```bash
cd <repository_name>
```
   *Replace <repository_name> with the name of the file you saved the repository in.*
   
3. Install Dependencies

   #### Run the following commands to install them:
_For React_
```
npm install
```
_For Storybook_
```
npx storybook@latest init
```
   - You will be prompted to choose between Vite and Webpack upon setup.
   - This repo is using Vite - `name: "@storybook/react-vite"`
### However, If you want to use Webpack
   - Go to .storybook/main.ts file
   - Make sure the name is as follows
```
framework: {
name: "@storybook/react-webpack",
options: {},
```
4. Run the Storybook Development Server

#### Start the Storybook development server by running:
```
npm run storybook
```
*This command will start the server, and you'll be able to access the Storybook UI in your web browser at a URL like http://localhost:6006.*

5. Explore and Test

   - Once the Storybook development server is running, you can explore and test your components in the Storybook UI.
   - Use your web browser to navigate to http://localhost:6006 (or the appropriate URL if configured differently).

6. Make Changes

   -If you want to make changes to your components, you can edit the source code in your local repository using your preferred code editor.

7. Building the Library

   - If you're satisfied with your changes and want to distribute the updated component library, you might need to build the library.
   - Check if there's a build script in your package.json. It might be something like: `"build-storybook": "storybook build"`
   - Then run this code
```
npm run build
```
*Running this script will create a build of your component library that can be distributed and used by others.*
