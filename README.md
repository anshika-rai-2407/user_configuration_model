# user_configuration_model
..

test_settings={
    'theme': 'light',
    'language': 'English',
    'font_size': 'medium',
    'notifications': 'enabled',
    'volume': 'high'
}

item = ('THEME', 'dark')


def add_setting(test_settings, item):
    key, value = item

    key = key.lower()
    value = value.lower()

    if key in test_settings:
        return f"Setting '{key}' already exists! Cannot add a new setting with this name."

    test_settings[key] = value

    return f"Setting '{key}' added with value '{value}' successfully!"

def update_setting(test_settings, item):
    key, value = item

    key = key.lower()
    value = value.lower()

    if key in test_settings:
        test_settings[key] = value
        return f"Setting '{key}' updated to '{value}' successfully!"

    else:
        return f"Setting '{key}' does not exist! Cannot update a non-existing setting."

def delete_setting(test_settings, item):
    key = item.lower()

    if key in test_settings:
        test_settings.pop(key)
        return f"Setting '{key}' deleted successfully!"

    else:
        return "Setting not found!"

def view_settings(test_settings):

    if not test_settings:
        return "No settings available."

    result = "Current User Settings:\n"

    for key, value in test_settings.items():
        result += f"{key.capitalize()}: {value}\n"

    return result
