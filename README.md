## Description

- Implemented deployment pipeline using GitHub Actions for CI/CD.
- Configured Nginx as a reverse proxy for FastAPI application.
- Set up fastapi.service with systemd for application process management.
- Deployed application on Azure Virtual Machine.
- Included a method to get book by id.

## Related Task

HNG12 Stage 2 Task(https://github.com/hng12-devbot/fastapi-book-project)

## Testing

- Ran pytest locally (all tests passed).
- Manually tested endpoints using Swagger which include:
	- Getting all previous books.
	- Creating a new book using the post request.
	- Getting a the new book by it's Id
- Tested an invalid request using an invalid Id.

## Notes

- Invited hng12-devbotops as a collaborator.
- Deployment URL: http://20.151.62.128

## Running the Application

1. Start the server:

```bash
uvicorn main:app
```

2. Access the API documentation:

- Swagger UI: http://localhost:8000/docs
- ReDoc: http://localhost:8000/redoc

## API Endpoints

### Books

- `GET /api/v1/books/` - Get all books
- `GET /api/v1/books/{book_id}` - Get a specific book
- `POST /api/v1/books/` - Create a new book
- `PUT /api/v1/books/{book_id}` - Update a book
- `DELETE /api/v1/books/{book_id}` - Delete a book

### Health Check

- `GET /healthcheck` - Check API status

## Book Schema

```json
{
  "id": 1,
  "title": "Book Title",
  "author": "Author Name",
  "publication_year": 2024,
  "genre": "Fantasy"
}
```

Available genres:

- Science Fiction
- Fantasy
- Horror
- Mystery
- Romance
- Thriller

## Running Tests

```bash
pytest
```

## Error Handling

The API includes proper error handling for:

- Non-existent books
- Invalid book IDs
- Invalid genre types
- Malformed requests

## Contributing

1. Fork the repository (https://github.com/Yusful-World/fastapi-book-project.git)
2. Create a feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit changes (`git commit -m 'Add AmazingFeature'`)
4. Push to branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## Support

For support, please open an issue in the GitHub repository.
