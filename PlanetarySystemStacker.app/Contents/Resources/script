#!/bin/bash

# Create 'PlanetarySystemStacker' directory in the user's Applications directory if it does not exist
APPLICATIONS_DIR="$HOME/Applications"
PROJECT_DIR="$APPLICATIONS_DIR/PlanetarySystemStacker"

if [ ! -d "$PROJECT_DIR" ]; then
    echo "Creating 'PlanetarySystemStacker' directory in the Applications folder..."
    mkdir -p "$PROJECT_DIR"
    echo "'PlanetarySystemStacker' directory created in '$APPLICATIONS_DIR'."
else
    echo "'PlanetarySystemStacker' directory already exists in '$APPLICATIONS_DIR'."
fi

# Change to the 'PlanetarySystemStacker' directory
cd "$PROJECT_DIR"

# Check if Python 3 is already installed
if ! command -v python3 &> /dev/null; then
    echo "Python 3 not found. Installing..."

    # Download the latest Python 3 installer from the official website
    curl -O https://www.python.org/ftp/python/3.11.5/python-3.11.5-macos11.pkg

    # Install Python 3 using the downloaded installer
    sudo installer -pkg python-3.11.5-macos11.pkg -target /

    # Clean up the installer file
    rm python-3.11.5-macos11.pkg

    echo "Python 3 installation complete."
else
    echo "Python 3 is already installed."
fi

# Check if Git is already installed
if ! command -v git &> /dev/null; then
    echo "Git not found. Installing..."

    # Download the latest Git installer from the official website
    curl -O https://github.com/git/git/releases/download/v2.41.0/git-2.41.0-intel-universal-macos13.pkg

    # Install Git using the downloaded installer
    sudo installer -pkg git-2.41.0-intel-universal-macos13.pkg -target /

    # Clean up the installer file
    rm git-2.41.0-intel-universal-macos13.pkg

    echo "Git installation complete."
else
    echo "Git is already installed."
fi

# Check if Python virtualenv is installed
if ! python3 -m venv --help &> /dev/null; then
    echo "Virtualenv not found. Installing..."

    # Install the virtualenv package using pip (ensuring pip is installed)
    python3 -m ensurepip --upgrade
    python3 -m pip install --upgrade pip
    python3 -m pip install virtualenv

    echo "Virtualenv installation complete."
else
    echo "Virtualenv is already installed."
fi

# Check if virtual environment 'pss' already exists inside the 'PlanetarySystemStacker' directory
if [ ! -d "$PROJECT_DIR/pss" ]; then
    echo "Creating a Python virtual environment named 'pss' inside '$PROJECT_DIR'..."
    python3 -m venv "$PROJECT_DIR/pss"
    echo "Virtual environment 'pss' created."
else
    echo "Virtual environment 'pss' already exists."
fi

# Activate the virtual environment
if [ -d "$PROJECT_DIR/pss" ]; then
    echo "Activating the virtual environment 'pss'..."
    
    # macOS uses a shell script to activate the virtual environment
    source "$PROJECT_DIR/pss/bin/activate"

    # Inform the user that the virtual environment is activated
    echo "Virtual environment 'pss' is now activated."
else
    echo "Virtual environment 'pss' could not be activated."
fi

# Check if the repository has already been cloned
if [ ! -d "$PROJECT_DIR/PlanetarySystemStacker" ]; then
    echo "Cloning the repository 'PlanetarySystemStacker' into '$PROJECT_DIR'..."
    git clone https://github.com/Rolf-Hempel/PlanetarySystemStacker.git "$PROJECT_DIR/PlanetarySystemStacker"

    # Inform the user about the cloned repository
    echo "Repository 'PlanetarySystemStacker' cloned into '$PROJECT_DIR/PlanetarySystemStacker'."
else
    echo "Repository 'PlanetarySystemStacker' already exists. Skipping clone."
fi

# Install dependencies if not already installed
dependencies=("numpy" "matplotlib" "psutil" "PyQt5" "scipy" "astropy" "scikit-image" "opencv-python-headless")

for dep in "${dependencies[@]}"; do
    if ! python3 -c "import ${dep}" &> /dev/null; then
        echo "Installing ${dep}..."
        pip3 install ${dep}
    else
        echo "${dep} is already installed."
    fi
done

echo "All dependencies checked and installed if needed."

# Navigate to the cloned repository directory
if [ -d "$PROJECT_DIR/PlanetarySystemStacker" ]; then
    cd "$PROJECT_DIR/PlanetarySystemStacker"
    echo "Navigated to 'PlanetarySystemStacker' directory."
else
    echo "Failed to navigate to 'PlanetarySystemStacker' directory."
fi

# Open the program (planetary_system_stacker.py) if it exists
if [ -f "$PROJECT_DIR/PlanetarySystemStacker/planetary_system_stacker/planetary_system_stacker.py" ]; then
    echo "Running the program: planetary_system_stacker.py"
    python "$PROJECT_DIR/PlanetarySystemStacker/planetary_system_stacker/planetary_system_stacker.py"
else
    echo "The file 'planetary_system_stacker.py' does not exist in the 'planetary_system_stacker' directory."
fi
