::if PSLICE_FIREBASE_SDK::
# Add Firebase libraries to the target using the function from the SDK.
add_subdirectory(${FIREBASE_CPP_SDK_DIR} bin/ EXCLUDE_FROM_ALL)

# The Firebase C++ library `firebase_app` is required,
# and it must always be listed last.

# Add the Firebase SDKs for the products you want to use in your app
# For example, to use Firebase Authentication and Firebase Realtime Database
set(firebase_libs
  firebase_analytics
  firebase_auth
  firebase_database
  firebase_app
)
target_link_libraries(${target_name} "${firebase_libs}")
::end::