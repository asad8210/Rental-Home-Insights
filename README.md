# Rental Insights - AI-Powered Rental Price Estimation

This is a Next.js application, that provides AI-powered rental price estimations for rooms.

## How it Works

The application follows a simple, multi-step process to generate a rental estimate:

1.  **Image Upload**: The user uploads one or more images of a room. The application supports up to 5 images to ensure a comprehensive analysis.

2.  **Feature Confirmation**: The user can specify additional structural features of the property, such as the number of rooms (1BHK/2BHK), or the presence of a balcony or attached bathroom.

3.  **AI Analysis**:
    *   The application's backend uses an AI model to detect objects and features within the uploaded images (e.g., furniture, appliances).
    *   A Genkit flow merges the detections from all images into a single, deduplicated list, keeping the detection with the highest confidence score for any duplicates.

4.  **Rent Calculation**: The system combines the AI-detected features with the user-confirmed structural features. It then calculates an estimated monthly rent range based on a predefined pricing database.

5.  **Result Display**: The final results are displayed to the user, including:
    *   The estimated rental price range.
    *   A list of all detected and confirmed features.
    *   An AI-generated explanation detailing how the features influenced the final price.

## Tech Stack

*   **Framework**: Next.js (with React Server Components)
*   **AI/Generative**: Google's Gemini models via Genkit
*   **UI**: ShadCN UI Components & Tailwind CSS
*   **Icons**: Lucide React

## Getting Started

Follow these steps to get the project running on your local machine.

### Prerequisites

*   Node.js (v18 or later recommended)
*   npm or yarn

### Installation

1.  Clone the repository to your local machine.
2.  Navigate to the project directory and install the required dependencies:

    ```bash
    npm install
    ```

### Running the Development Servers

You'll need to run two separate processes in two different terminals for the full application to work.

1.  **Start the Next.js Frontend:**
    This command starts the main web application.

    ```bash
    npm run dev
    ```
    The application will be available at [http://localhost:9002](http://localhost:9002).

2.  **Start the Genkit AI Flows:**
    This command runs the AI backend flows, allowing the Next.js app to communicate with them.

    ```bash
    npm run genkit:dev
    ```

Once both servers are running, you can open your browser and start using the application.
